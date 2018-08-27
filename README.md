## REACT项目基础模板    
### 项目构建流程 **通过cli构建项目** 如果一个项目需要从0开始构建的话，可以按照以下流程操作。   
1. 安装node.js和npm    
   根据操作系统下载对应的最新的稳定版node.js并安装。安装完成后，在命令行运行如下命令。 
    ```    
      // 查看node.js的版本，如果出现版本信息，证明安装成功    
      node -version    
      // 查看npm的版本，如果出现版本信息，证明npm安装成功    
      npm -v    
    ```  
2. 安装create-react-app命令行工具 在命令行输入如下命令，安装react的命令行工具。 
    ```
      // 安装react的命令行工具    
      npm install -g create-react-app    
    ```
3. 通过create-react-app初始化项目 通过命令行进入需要创建项目的目录，运行如下命令，会初始化名称为project的项目。初始化过程中，命令行会有项目配置的相关选择，可以根据自己的需求配置。 
    ```
      // 初始化名称为project的项目    
      create-react-app project    
    ```
  
 4. 安装react-app-rewired模块  
    通过安装react-app-rewired模块，可以重写项目的配置文件。  
    ```
      // 初始化名称为project的项目    
      npm install react-app-rewired --save-dev   
    ```  
  
 5. 安装react-app-rewire-less模块  
    通过安装react-app-rewire-less模块，使项目支持less语言。  
    ```
      // 安装react-app-rewire-less模块    
      npm install react-app-rewire-less --save-dev   
    ```  
  6. 安装react-app-rewire-scss模块  
    通过安装react-app-rewire-scss模块，使项目支持sass语言。  
    ```
      // 安装react-app-rewire-scss模块    
      npm install react-app-rewire-scss --save-dev   
    ```  
 7. 在根目录下新建config-overrides.js文件并复制一下内容
    ```
      const rewireSass = require('react-app-rewire-scss');  
      const rewireLess = require('react-app-rewire-less');  
      module.exports = function override(config, env) {  
        config = rewireSass(config, env);  
        config = rewireLess(config, env);  
        //do stuff with the webpack config...  
        return config;  
      }   
    ```  