[参考文档](https://blog.51cto.com/u_15127666/2785788)
# 实例API
```js
/**
 * 返回name对应的模块实例
 * @param { string } name 模块名
 * @param { boolean } strict 启用严格模式。false：缺少的模块解析为null返回；true：抛出异常
 */
this.bpmnModeler.get(name, strict);

// 内部调用了importXML方法，读取内部的默认xml字符串
this.bpmnModeler.createDiagram();

// 清空
this.bpmnModeler.clear();

// 脱离dom
this.bpmnModeler.detach();

// 💡 获取流程定义
this.bpmnModeler.getDefinitions();

// 获取扩展功能模块列表
this.bpmnModeler.getModules();
/*
 * 
 * @param { ModdleElement<BPMNDiagram>|string } [bpmnDiagram] 要呈现的BPMN图或图的ID（如果未提供，将呈现第一个）
 */
this.bpmnModeler.importDefinitions(definitions, bpmnDiagram);

this.bpmnModeler.importXML(xml, callback);

this.bpmnModeler.saveSVG(callback);

this.bpmnModeler.saveXML(callback);
```


# [[内置模块]]