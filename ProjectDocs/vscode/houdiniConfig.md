# vscode 配置houdini开发环境
* 1.打开VSCode，使用快捷键“Ctrl + Shift + P”或者点击左下角的齿轮图标选择命令面板，输入“settings.json”进行搜索,
然后点击 "打开用户设置"即可进入用户设置 settings.json 文件
* 2 将下面代码粘贴覆盖进 settings.json文件中,然后保存重启vscode

```js
{
    "python.linting.pylintEnabled": false,
    "python.linting.flake8Enabled": true,
    "editor.renderWhitespace": "all",
    "editor.mouseWheelZoom": true,
    "editor.rulers": [79, 120, 150],
    "editor.tabSize": 4,
    "window.title": "${activeEditorLong}",
    "python.autoComplete.extraPaths": [
        "/opt/hfs18.5.499/houdini/python2.7libs",
        "/opt/hfs18.5.499/python/lib/python2.7",
        "/opt/hfs18.5.499/python/lib/python2.7/site-packages",
        "/opt/hfs18.5.499/python/lib/python2.7/site-packages-forced",
        "/opt/hfs18.5.499/python/lib/python2.7/site-packages-forced/PySide2",
    ],
    "python.analysis.extraPaths": [
        "/opt/hfs18.5.499/houdini/python2.7libs",
        "/opt/hfs18.5.499/python/lib/python2.7",
        "/opt/hfs18.5.499/python/lib/python2.7/site-packages",
        "/opt/hfs18.5.499/python/lib/python2.7/site-packages-forced",
        "/opt/hfs18.5.499/python/lib/python2.7/site-packages-forced/PySide2",
    ],
    "tabnine.experimentalAutoImports": true,
    "workbench.colorCustomizations": {},
    "workbench.iconTheme": "material-icon-theme",
}
```