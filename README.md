react-panel
========================

A Panel component written in React.

[Click here for the demo](https://wmira.github.io/react-panel) or see index.html for usage.

## Development

1. npm install -g live-server
2. npm install
3. hack away

## How to use

```javascript
    var Panel =require("react-panel");
    
    var panel1 = Panel.render({ contentStr:document.getElementById("content1").innerHTML, title: "Panel Demo 1"},"panel1");
    var panel2 = Panel.render({ contentStr:document.getElementById("content2").innerHTML, title: "Enter Some Form Values"},"panel2");
    
    var toolboxActions =  [
        { title: "Reload", className: "fa fa-refresh", "data-action-name" : "reload" },
        { title: "Hide", className: "fa fa-chevron-down", "data-action-name" : "hide" }
    ];
    
    var actionListener = function(e) {
        alert("on click: " + e.target.getAttribute("data-action-name"));
    };
    
    var panel3 = Panel.render({ titleIcon: "fa fa-bar-chart", clickListener:actionListener, toolbox: toolboxActions,
        contentStr:document.getElementById("content1").innerHTML, title:
            "Panel Toolbox Demo"},"panel3");
            
    panel3.on("click","a > .fa-refresh",function() {
            alert("refresh");
    });

    panel3.on("click","a > .fa-chevron-down",function() {
        alert("hide");
    });
    
    //Render a react component as body
    React.render(
        <Panel.cls title="React Component Body Example">
            <div style={{'fontWeight': 'bold' }}>This is a react component.</div>
        </Panel.cls>,
                document.getElementById("panel4")
    )
```

Changelog
----------

##### 0.0.4
- Body can now be composed using <Panel.cls></Panel>

