---
title: "扩展任务列表 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "任务列表"
ms.assetid: 9d84c9c4-7796-4fa1-86f8-22d077b79f7e
caps.latest.revision: 17
caps.handback.revision: 17
manager: "douge"
---
# 扩展任务列表
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **任务列表** 允许用户：添加自定义编程任务；查看链接到代码中的行的 任务注释 ；创建并查看任务消息的自定义类别。  
  
 通过已命名的服务来处理任务 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList>，可实现 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> 和 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList2>。 若要使用**任务列表**基本功能，必须通过实现 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider> 创建一个任务提供程序。  
  
 通过调用 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RegisterTaskProvider%2A> 向 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList> 服务注册任务提供程序，这将返回一个 cookie 值，该值必须用来在所有的后续事务中唯一标识任务提供程序。  
  
 每个任务提供程序实现负责维护任务的内部列表。 任务提供程序可以调用**任务列表** 上的 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RefreshTasks%2A> 以更新显示的任务列表。 出现此情况时：  
  
1.  服务通过使用方法 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider.EnumTaskItems%2A> 回调到任务提供程序。  
  
2.  任务提供程序 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider.EnumTaskItems%2A> 的实现返回一个 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumTaskItems> 对象。  
  
3.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumTaskItems> 对象循环访问 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem> 对象的集合。  
  
4.  然后 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList> 服务更新**任务列表**显示。  
  
 其他功能可用。<xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider3> 接口使每个任务提供程序能提供其自己的自定义列集。  
  
## 示例  
 以下的代码示例演示任务提供程序的实现。  
  
```vb#  
Class TaskProvider Implements ITaskProvider Implements IVsSolutionEvents Public Sub New(ByVal provider As IServiceProvider) _imageList.ImageSize = New Size(9, 16) _imageList.Images.AddStrip(Resources.priority) _imageList.TransparentColor = Color.FromArgb(0, 255, 0) _serviceProvider = provider Dim taskList As IVsTaskList = TryCast(_serviceProvider.GetService(GetType(SVsTaskList)), IVsTaskList) Dim hr As Integer = taskList.RegisterTaskProvider(Me, _cookie) Debug.Assert(hr = VSConstants.S_OK, "RegisterTaskProvider did not return S_OK.") Debug.Assert(_cookie <> 0, "RegisterTaskProvider did not return a nonzero cookie.") SetCommandHandlers() ListenForProjectUnload() End Sub #Region "ITaskProvider Members" Public Sub AddResult(ByVal result As IScanResult, ByVal projectFile As String) Dim fullPath As String = result.FilePath If Not Path.IsPathRooted(fullPath) Then fullPath = Utilities.AbsolutePathFromRelative(fullPath, Path.GetDirectoryName(projectFile)) End If If result.Scanned Then For Each hit As IScanHit In result.Results If hit.Warning IsNot Nothing AndAlso hit.Warning.Length > 0 Then ' See if we've warned about this term before; ' if so, don't warn again. If _termsWithDuplicateWarning.Find(Function(ByVal item As String) [String].Compare(item, hit.Term.Text, StringComparison.OrdinalIgnoreCase) = 0) Is Nothing Then _tasks.Add(New Task(hit.Term.Text, hit.Term.Severity, hit.Term.[Class], hit.Warning, "", "", _ -1, -1, "", "", Me, _serviceProvider)) _termsWithDuplicateWarning.Add(hit.Term.Text) End If End If _tasks.Add(New Task(hit.Term.Text, hit.Term.Severity, hit.Term.[Class], hit.Term.Comment, hit.Term.RecommendedTerm, fullPath, _ hit.Line, hit.Column, projectFile, hit.LineText, Me, _serviceProvider)) Next Else _tasks.Add(New Task("", 1, "", [String].Format(CultureInfo.CurrentUICulture, Resources.FileNotScannedError, fullPath), "", fullPath, _ -1, -1, projectFile, "", Me, _serviceProvider)) End If Refresh() End Sub Public Sub Clear() _tasks.Clear() Refresh() End Sub Public Sub SetAsActiveProvider() Dim taskList As IVsTaskList2 = TryCast(_serviceProvider.GetService(GetType(SVsTaskList)), IVsTaskList2) Dim ourGuid As Guid = _providerGuid Dim hr As Integer = taskList.SetActiveProvider(ourGuid) Debug.Assert(hr = VSConstants.S_OK, "SetActiveProvider did not return S_OK.") End Sub Public Sub ShowTaskList() Dim shell As IVsUIShell = TryCast(_serviceProvider.GetService(GetType(SVsUIShell)), IVsUIShell) Dim dummy As Object = Nothing Dim cmdSetGuid As Guid = VSConstants.GUID_VSStandardCommandSet97 Dim hr As Integer = shell.PostExecCommand(cmdSetGuid, CInt(VSConstants.VSStd97CmdID.TaskListWindow), 0, dummy) Debug.Assert(hr = VSConstants.S_OK, "SetActiveProvider did not return S_OK.") End Sub ''' <summary> ''' Returns an image index between 0 and 2 inclusive corresponding ''' to the specified severity. ''' </summary> Public Shared Function GetImageIndexForSeverity(ByVal severity As Integer) As Integer Return Math.Max(1, Math.Min(3, severity)) - 1 End Function Public ReadOnly Property IsShowingIgnoredInstances() As Boolean Get Return _showingIgnoredInstances End Get End Property #End Region #Region "IVsTaskProvider Members" Public Function EnumTaskItems(ByRef ppenum As IVsEnumTaskItems) As Integer ppenum = New TaskEnumerator(_tasks, IsShowingIgnoredInstances) Return VSConstants.S_OK End Function <DllImport("comctl32.dll")> _ Private Shared Function ImageList_Duplicate(ByVal original As IntPtr) As IntPtr End Function Public Function ImageList(ByRef phImageList As IntPtr) As Integer phImageList = ImageList_Duplicate(_imageList.Handle) Return VSConstants.S_OK End Function Public Function OnTaskListFinalRelease(ByVal pTaskList As IVsTaskList) As Integer If (_cookie <> 0) AndAlso (pTaskList IsNot Nothing) Then Dim hr As Integer = pTaskList.UnregisterTaskProvider(_cookie) Debug.Assert(hr = VSConstants.S_OK, "UnregisterTaskProvider did not return S_OK.") End If Return VSConstants.S_OK End Function Public Function ReRegistrationKey(ByRef pbstrKey As String) As Integer pbstrKey = "" Return VSConstants.E_NOTIMPL End Function Public Function SubcategoryList(ByVal cbstr As UInteger, ByVal rgbstr As String(), ByRef pcActual As UInteger) As Integer pcActual = 0 Return VSConstants.E_NOTIMPL End Function End Class  
```  
  
```c#  
class TaskProvider : ITaskProvider, IVsSolutionEvents { public TaskProvider(IServiceProvider provider) { _imageList.ImageSize = new Size(9, 16); _imageList.Images.AddStrip(Resources.priority); _imageList.TransparentColor = Color.FromArgb(0, 255, 0); _serviceProvider = provider; IVsTaskList taskList = _serviceProvider.GetService(typeof(SVsTaskList)) as IVsTaskList; int hr = taskList.RegisterTaskProvider(this, out _cookie); Debug.Assert(hr == VSConstants.S_OK, "RegisterTaskProvider did not return S_OK."); Debug.Assert(_cookie != 0, "RegisterTaskProvider did not return a nonzero cookie."); SetCommandHandlers(); ListenForProjectUnload(); } #region ITaskProvider Members public void AddResult(IScanResult result, string projectFile) { string fullPath = result.FilePath; if (!Path.IsPathRooted(fullPath)) { fullPath = Utilities.AbsolutePathFromRelative(fullPath, Path.GetDirectoryName(projectFile)); } if (result.Scanned) { foreach (IScanHit hit in result.Results) { if (hit.Warning != null && hit.Warning.Length > 0) { // See if we've warned about this term before; // if so, don't warn again. if (null == _termsWithDuplicateWarning.Find( delegate(string item) { return String.Compare(item, hit.Term.Text, StringComparison.OrdinalIgnoreCase) == 0; })) { _tasks.Add(new Task(hit.Term.Text, hit.Term.Severity, hit.Term.Class, hit.Warning, "", "", -1, -1, "", "", this, _serviceProvider)); _termsWithDuplicateWarning.Add(hit.Term.Text); } } _tasks.Add(new Task(hit.Term.Text, hit.Term.Severity, hit.Term.Class, hit.Term.Comment, hit.Term.RecommendedTerm, fullPath, hit.Line, hit.Column, projectFile, hit.LineText, this, _serviceProvider)); } } else { _tasks.Add(new Task("", 1, "", String.Format(CultureInfo.CurrentUICulture, Resources.FileNotScannedError, fullPath), "", fullPath, -1, -1, projectFile, "", this, _serviceProvider)); } Refresh(); } public void Clear() { _tasks.Clear(); Refresh(); } public void SetAsActiveProvider() { IVsTaskList2 taskList = _serviceProvider.GetService(typeof(SVsTaskList)) as IVsTaskList2; Guid ourGuid = _providerGuid; int hr = taskList.SetActiveProvider(ref ourGuid); Debug.Assert(hr == VSConstants.S_OK, "SetActiveProvider did not return S_OK."); } public void ShowTaskList() { IVsUIShell shell = _serviceProvider.GetService(typeof(SVsUIShell)) as IVsUIShell; object dummy = null; Guid cmdSetGuid = VSConstants.GUID_VSStandardCommandSet97; int hr = shell.PostExecCommand(ref cmdSetGuid, (int)VSConstants.VSStd97CmdID.TaskListWindow, 0, ref dummy); Debug.Assert(hr == VSConstants.S_OK, "SetActiveProvider did not return S_OK."); } /// <summary> /// Returns an image index between 0 and 2 inclusive corresponding /// to the specified severity. /// </summary> public static int GetImageIndexForSeverity(int severity) { return Math.Max(1, Math.Min(3, severity)) - 1; } public bool IsShowingIgnoredInstances { get { return _showingIgnoredInstances; } } #endregion #region IVsTaskProvider Members public int EnumTaskItems(out IVsEnumTaskItems ppenum) { ppenum = new TaskEnumerator(_tasks, IsShowingIgnoredInstances); return VSConstants.S_OK; } [DllImport("comctl32.dll")] static extern IntPtr ImageList_Duplicate(IntPtr original); public int ImageList(out IntPtr phImageList) { phImageList = ImageList_Duplicate(_imageList.Handle); return VSConstants.S_OK; } public int OnTaskListFinalRelease(IVsTaskList pTaskList) { if ((_cookie != 0) && (null != pTaskList)) { int hr = pTaskList.UnregisterTaskProvider(_cookie); Debug.Assert(hr == VSConstants.S_OK, "UnregisterTaskProvider did not return S_OK."); } return VSConstants.S_OK; } public int ReRegistrationKey(out string pbstrKey) { pbstrKey = ""; return VSConstants.E_NOTIMPL; } public int SubcategoryList(uint cbstr, string[] rgbstr, out uint pcActual) { pcActual = 0; return VSConstants.E_NOTIMPL; } }  
```  
  
## 请参阅  
 [创建自定义任务列表视图](/visual-cpp/misc/creating-custom-task-list-views)   
 [如何：创建任务列表的自定义类别](../misc/how-to-create-custom-categories-of-task-lists.md)