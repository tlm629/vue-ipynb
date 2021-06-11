# vue-ipynb
一个Demo，利用 `jsvine/notebookjs` 在VUE中展示 `ipynb` 文件，并作代码高亮。
Demo to view a `.ipynb` (python notebook) file with VUE.


# How to Use

### Install
```
npm install marked ansi_up dompurify jsdom
npm install prismjs 
npm install babel-plugin-prismjs 
```

### Config 
Config `.babelrc` file of your VUE project

```json
{
    "plugins": [
        [
            "prismjs",
            {
                "languages": ["html", "css", "javascript", "python"],
                "plugins": ["line-numbers"]
            }
        ]
    ]
}
```

### Copy files
Copy this files to project:
- prism.css
- notebook.js

### Run and View .ipynb file
```
npm install
npm run serve
```
view:
http://localhost:8080/ 


# Thanks
Many thanks to the following users for catching bugs, fixing typos, and proposing useful features:
https://github.com/jsvine/notebookjs
https://prismjs.com/