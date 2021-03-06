---
order: 2
title:
  zh-CN: 绑定数据源
  en-US: DataSet Binding
---

## zh-CN

绑定数据源

## en-US

DataSet Binding

````jsx
import { DataSet, CheckBox } from 'choerodon-ui/pro';

function handleChange({ name, value, oldValue }) {
  console.log(`[dataset:${name}]`, value, '[oldValue]', oldValue);
}

const data = [{
  bind: 'A',
}];

class App extends React.Component {
  ds = new DataSet({
    fields: [
      { name: 'bind', multiple: true },
      { name: 'bind2', type: 'boolean', label: '是否开启' }, // 组件没有children会用label替代
      { name: 'bind3', type: 'boolean', trueValue: 'Y', falseValue: 'N' },
    ],
    data,
    events: {
      update: handleChange,
    },
  });

  render() {
    return (
      <div>
        <CheckBox dataSet={this.ds} name="bind" value="A">A</CheckBox>
        <CheckBox dataSet={this.ds} name="bind" value="B">B</CheckBox>
        <CheckBox dataSet={this.ds} name="bind" value="C">C</CheckBox>
        <CheckBox dataSet={this.ds} name="bind2" /> 
        <CheckBox dataSet={this.ds} name="bind3">是否展开</CheckBox>
      </div>
    );
  }
}

ReactDOM.render(
  <App />,
  mountNode
);
````
