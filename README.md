# core.loader.components

load components from plugin definitions.

related to <a href="https://github.com/ido-ofir/core.type.component">core.type.component</a>

```js
let core = new require('core.constructor')();
 
core.plugin(
    require('core.loader.components')
);

// plugins can now declare actions on the plugin definition object:
core.plugin({
    name: 'test',
    components: [
        {
            name: 'SomeComponent',
            get(){
                return {
                    render(){
                        return <div> OK </div>
                    }
                };
            }
        }
    ]
});

// require this new component
core.require(['test.SomeComponent'], SomeComponent => { ... })

// exists on core.components
core.components['test.SomeComponent'];

// exists on plugin components
core.plugins.test.components.SomeComponent;
```
