# Mermaid: Block Deployment Layout

````md
```mermaid
block
    columns 2
    block:frontend
        columns 1
        WebUI["Web UI"]
        AdminUI["Admin UI"]
    end
    block:backend
        columns 1
        API
        Worker
    end
```
````

Notes:

- Use for layered deployment layouts and simple component groupings.
- Block diagrams use the `block` keyword and more manual layout control.
