---
title: 创建 Node.js 和 React 应用 - Visual Studio | Microsoft Docs
description: 本教程会在 Visual Studio 中创建 Node.js 和 React 应用
ms.custom: mvc
ms.date: 02/19/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-nodejs
ms.tgt_pltfrm: ''
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 0d48d8ddb9c63ca83153ae4fe1b28015217bb072
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tutorial-create-a-nodejs-and-react-app-in-visual-studio"></a>教程：在 Visual Studio 中创建 Node.js 和 React 应用
通过 Visual Studio 可以轻松创建 Node.js 项目并利用 IntelliSense 和其他支持 Node.js 的内置功能。 此 Visual Studio 教程将从 Visual Studio 模板创建 Node.js Web 应用程序项目。 然后，使用 React 创建一个简单的应用程序。 

在本教程中，你将了解：
> [!div class="checklist"]
> * 创建 Node.js 项目
> * 添加 npm 包
> * 将 React 代码添加到应用
> * 转译 JSX
> * 附加调试器

## <a name="prerequisites"></a>系统必备

* 须安装 Visual Studio 且具有 Node.js 开发工作负载。

    如果尚未安装 Visual Studio，请在[此处](http://www.visualstudio.com)免费安装。

    如果需要安装工作负载，但已有 Visual Studio，则单击“新建项目”对话框左窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 选择“Node.js 开发”工作负载，然后选择“修改”。

* 须安装 Node.js 运行时。

    如果未安装，请从 [Node.js](https://nodejs.org/en/download/) 网站安装 LTS 版本。 一般情况下，Visual Studio 会自动检测已安装的 Node.js 运行时。 如果系统未检测到已安装运行时，则可以将项目配置为引用属性页中已安装的运行时（创建项目后，右键单击项目节点并选择“属性”）。

    本教程已使用版本 8.9.4 进行测试。

## <a name="create-a-project"></a>创建项目
首先，创建一个 Node.js Web 应用程序项目。

1. 打开 Visual Studio 2017。  

1. 在顶部菜单栏，依次选择“文件” > “新建” > “项目...”。  

1. 在“新建项目”对话框的左窗格中，展开“JavaScript”，然后选择“Node.js”。 在中间窗格中，选择“空白 Node.js Web 应用程序”，键入名称“NodejsWebAppBlank”，然后选择“确定”。   

     如果未看到“空白 Node.js Web 应用程序”项目模板，须先安装 Node.js 开发工作负载。 

    Visual Studio 创建新的解决方案并打开项目。

    ![解决方案资源管理器中的 Node.js 项目](../nodejs/media/tutorial-nodejs-react-project-structure.png)  

    - 粗体突出显示的是项目，其名称是在“新建项目”对话框中指定的名称。 在文件系统中，此项目由项目文件夹中的 .njsproj 文件表示。 可以右键单击项目并选择“属性”，设置与项目相关的属性和环境变量。 可以使用其他开发工具执行往返，因为项目文件不对 Node.js 项目源做出自定义更改。

    - 顶层是一个解决方案，它与项目默认同名。 解决方案在磁盘上由 .sln 文件表示，是一个或多个相关项目的容器。

    - Npm 节点显示任何已安装的 npm 包。 可以右键单击 npm 节点搜索 npm 包，并使用对话框安装 npm 包。

    - 项目文件（例如 server.js）显示在项目节点下。 server.js 是项目启动文件。

## <a name="add-npm-packages"></a>添加 npm 包

此应用需要大量 npm 模块才能正常运行。

* react
* react-dom
* express
* path
* ts-loader
* typescript
* webpack
* webpack-cli

1. 在解决方案资源管理器（右窗格）中，右键单击项目中的“npm”节点并选择“安装新的 npm 包”。

    在“安装新的 npm 包”对话框中，可以选择安装最新的包版本，或者指定版本。 如果选择安装这些包的当前版本，但是之后发生意外错误，那么可能需要安装稍后步骤中介绍的包版本。

1. 在“安装新的 npm 包”对话框中，搜索 react 包并单击“安装包”进行安装。

    ![安装 npm 包](../nodejs/media/tutorial-nodejs-react-install-packages.png)

    “输出”窗口显示包的安装进度。 安装后，包会出现在“npm”节点下。

    项目的 package.json 文件中的信息更新为新的包信息（包括包版本）。

1. 将以下代码复制到 package.json，而不用使用 UI 一个一个搜索并添加其余的包。 使用此代码替换 `dependencies` 部分：

    ```js
    "dependencies": {
      "express": "4.16.2",
      "path": "0.12.7",
      "react": "16.2.0",
      "react-dom": "16.2.0",
      "ts-loader": "4.0.1",
      "typescript": "2.7.2",
      "webpack": "4.1.1",
      "webpack-cli": "2.0.11"
    }
    ```

1. 右键单击项目中的“npm”节点，然后选择“安装缺少的 npm 包”。

    “输出”窗口显示包的安装进度。

    以下安装后显示在解决方案资源管理器中的 npm 模块。

    ![npm 包](../nodejs/media/tutorial-nodejs-react-npm-modules.png) 

    > [!NOTE]
    > 如果想要使用命令行安装 npm 包，则右键单击项目节点并选择“在此处打开命令提示符”。 使用标准的 Node.js 命令安装包。

## <a name="add-project-files"></a>添加项目文件

在这些步骤中，将四个新文件添加到项目。

* *app.tsx*
* *webpack-config.js*
* index.html
* *tsconfig.json*

对于此简单应用，将新建项目文件添加到项目根中。 （在大多数应用中，通常将文件添加到子文件夹并相应调整相对路径引用。）

1. 在解决方案资源管理器中，右键单击项目“NodejsWebAppBlank”并选择“添加” > “新项”。

1. 在“添加新项”对话框中，选择“TypeScript JSX 文件”，键入名称“app.tsx”，然后单击“确定”。

1. 重复上述步骤，添加 webpack-config.js。

1. 重复相同步骤将 index.html 添加到项目。 选择“HTML 文件”，而不是 JavaScript 文件。

1. 重复相同步骤将 tsconfig.json 添加到项目。 选择“TypeScript JSON 配置文件”，而不是 JavaScript 文件。

## <a name="add-app-code"></a>添加应用代码

1. 打开 server.js 并将代码替换为以下代码：

    ```javascript
    'use strict';
    var path = require('path');
    var express = require('express');

    var app = express();

    var staticPath = path.join(__dirname, '/');
    app.use(express.static(staticPath));

    // Allows you to set port in the project properties.
    app.set('port', process.env.PORT || 3000);

    var server = app.listen(app.get('port'), function() {
        console.log('listening');
    });
    ```

   前面的代码使用 Express 启动 Node.js 作为 Web 应用程序服务器。 此代码将端口设置为在项目属性中配置的端口号（默认情况下，属性中的端口配置为 1337）。 若要打开项目属性，请右键单击解决方案资源管理器中的项目，然后选择“属性”。

1. 打开 app.tsx 并添加以下代码：

    ```javascript
    declare var require: any
    
    var React = require('react');
    var ReactDOM = require('react-dom');

    class Hello extends React.Component {
        render() {
            return (
                <h1>Welcome to React!!</h1>
            );
        }
    }

    ReactDOM.render(<Hello />, document.getElementById('root'));
    ```

    前面的代码使用 JSX 语法和 React 显示简单的消息。

1. 打开 index.html 并将“body”部分替换为以下代码：

    ```html
    <body>
        <div id="root"></div>
        <!-- scripts -->
        <script src="./dist/app-bundle.js"></script>
    </body>
    ```

    此 HTML 页加载 app-bundle.js，其中包含转译为纯文本 JavaScript 的 JSX 和 React 代码。 目前，app-bundle.js 是一个空文件。 在下一部分中，将配置选项以转译代码。

## <a name="configure-webpack-and-typescript-compiler-options"></a>配置 webpack 和 TypeScript 编译器选项

在前述步骤中，将 webpack-config.js 添加到了项目。 接下来要添加 webpack 配置代码。 将添加一个简单的 webpack 配置，以指定输入文件 (app.tsx) 和输出文件 (app-bundle.js)，用于捆绑 JSX 并将其转译为纯文本 JavaScript。 为进行转译，还要配置某些 TypeScript 编译器选项。 此代码是基本配置，用作有关 webpack 和 TypeScript 编译器的简介。

1. 在解决方案资源管理器中，打开 webpack config.js 并添加以下代码。

    ```json
    module.exports = {
        devtool: 'source-map',
        entry: "./app.tsx",
        mode: "development",
        output: {
            filename: "./app-bundle.js"
        },
        resolve: {
            extensions: ['.Webpack.js', '.web.js', '.ts', '.js', '.jsx', '.tsx']
        },
        module: {
            rules: [
                {
                    test: /\.tsx$/,
                    exclude: /(node_modules|bower_components)/,
                    use: {
                        loader: 'ts-loader'
                    }
                }
            ]
        }
    }
    ```

    webpack 配置代码指示 Webpack 使用 TypeScript 加载程序转译 JSX。

1. 打开 tsconfig.json 并添加以下代码，用于指定 TypeScript 编译器选项：

    ```json
    {
      "compilerOptions": {
        "noImplicitAny": false,
        "module": "commonjs",
        "noEmitOnError": true,
        "removeComments": false,
        "sourceMap": true,
        "target": "es5",
        "jsx": "react"
      },
      "exclude": [
        "node_modules"
      ],
      "files": [
        "app.tsx"
      ]
    }
    ```

    将 app.tsx 指定为源文件。

## <a name="transpile-the-jsx"></a>转译 JSX

1. 在解决方案资源管理器中，右键单击项目节点，并选择“在此处打开命令提示符”。

1. 在命令提示符处，键入下列命令：

    `node_modules\.bin\webpack app.tsx --config webpack-config.js`

    命令提示符窗口显示结果。

    ![运行 webpack](../nodejs/media/tutorial-nodejs-react-run-webpack.png) 

    如果看到错误而不是前面的输出，则必须在应用开始运行之前解决这些错误。 如果 npm 包版本不是本教程中所示的版本，则可能引发错误。 修复错误的一种方法是使用前面步骤中使用的版本。 此外，如果所使用的一个或多个包版本是已弃用的版本，并导致发生错误，则可能需要安装较新版本以消除错误。

1. 在解决方案资源管理器中，右键单击项目节点并选择“添加” > “现有文件夹”，然后选择 dist 文件夹并单击“选择文件夹”。

    Visual Studio 将 dist 文件夹添加到项目中，其中包含 app-bundle.js 和 app-bundle.js.map。

1. 打开 app-bundle.js，查看转译的 JavaScript 代码。

1. 如果系统提示从外部重新加载已修改的文件，请单击“全是”。

    ![加载已修改的文件](../nodejs/media/tutorial-nodejs-react-reload-files.png) 

每次对 app.tsx 进行更改时，必须重新运行 webpack 命令。

## <a name="run-the-app"></a>运行应用

1. 请确保将 Chrome 选为当前的调试目标。

    ![选择 Chrome 作为调试目标](../nodejs/media/tutorial-nodejs-react-debug-target.png)  

1. 若要运行应用，请按 F5（“调试” > “开始调试”）或者绿色箭头按钮。

    此时 Node.js 控制台窗口打开，并显示调试器正在侦听的端口。

    Visual Studio 通过启动启动文件 server.js 来启动应用。

    ![在浏览器中运行 React](../nodejs/media/tutorial-nodejs-react-running-react.png) 

1. 关闭浏览器窗口。

1. 关闭控制台窗口。

## <a name="set-a-breakpoint-and-run-the-app"></a>设置断点并运行应用

1. 在 server.js 中，单击 `staticPath` 声明左侧的滚动条槽以设置断点：

    ![设置断点](../nodejs/media/tutorial-nodejs-react-set-breakpoint.png) 

    断点是可靠调试的最基本和最重要的功能。 断点指示 Visual Studio 应在哪个位置挂起你的运行代码，以使你可以查看变量的值或内存的行为，或确定代码的分支是否运行。 

1. 若要运行应用，请按 F5（“调试” > “启动调试”）。

    调试器将在设置的断点处暂停（当前语句用黄色标记）。 现在，可使用调试程序窗口（例如“局部变量”和“监视”窗口），通过将鼠标悬停在当前范围内的变量上来检查应用的状态。

1. 按 F5 继续。

1. 如果想要使用 Chrome 开发人员工具，请按 F12。 可使用这些工具检查 DOM 并与使用 JavaScript 控制台的应用进行交互。

1. 关闭 Web 浏览器和控制台。

## <a name="set-and-hit-a-breakpoint-in-the-client-side-react-code"></a>设置并命中客户端 React 代码中的断点

在前面的部分中，已将调试器附加到服务器端 Node.js 代码。 若要从 Visual Studio 附加调试器并在客户端 React 代码中命中断点，调试器需协助标识正确的进程。 以下是实现此目的的一种方法。

1. 关闭所有 Chrome 窗口。

1. 从 Windows“启动”按钮打开“运行”命令（右键单击并选择“运行”），然后输入以下命令：

    `chrome.exe --remote-debugging-port=9222`

    这样在启动 Chrome 时会同时启用调试。

1. 如下图所示，切换到 Visual Studio 并在 `render()` 函数的 app-bundle.js 代码中设置断点：

    ![设置断点](../nodejs/media/tutorial-nodejs-react-set-breakpoint-client-code.png) 

1. 在选择 Chrome 作为 Visual Studio 中调试目标的情况下，按 Ctrl+F5（“调试” > “启动时不调试”）在浏览器中运行应用。

    应用随即在新的浏览器选项卡中打开。

1. 选择“调试” > “附加到进程”。

1. 在“附加到进程”对话框中，选择“附加到”字段中的“Webkit 代码”，在筛选框中键入“chrome”以筛选搜索结果。

1. 使用正确的主机端口（此例中为 1337）选择 Chrome 进程，然后单击“附加”。

    ![附加到进程](../nodejs/media/tutorial-nodejs-react-attach-to-process.png) 

    当 DOM 资源管理器和 JavaScript 控制台在 Visual Studio 中打开，表明已正确附加调试程序。 这些调试工具类似于 Chrome 开发人员工具和 Edge 的 F12 工具。

1. 由于已执行有断点的代码，因此要刷新浏览器页面以命中断点。

    在调试器中暂停时，可以通过在变量上悬停光标并使用调试器窗口，检查应用状态。 逐句通过代码（F5、F10 和 F11），推进调试器进度。

    可能会在 app-bundle.js 中或在 app.tsx 中断点的映射位置处命中断点，具体取决于环境和浏览器状态。 无论在哪里命中，均可单步执行代码并检查变量。 （如果中途需访问 .tsx 文件中的代码但又无法执行此操作，可尝试使用 `debugger;` 语句或在 Chrome 开发人员工具中设置断点。）

    > [!TIP]
    > 首次通过这些步骤附加到进程后，可选择“调试” > “重新附加到进程”，快速重新附加到 Visual Studio 2017 中的同一进程。

## <a name="next-steps"></a>后续步骤 

本教程介绍了如何创建 Node.js 和 React 应用、转译 JSX 和进行调试。 若要了解有关“针对 Visual Studio 的 Node.js 工具”的详细信息，请参阅 Wiki 页。

> [!div class="nextstepaction"]
> [适用于 Visual Studio 的 Node.js 工具](https://github.com/Microsoft/nodejstools)