---
category: Components
cols: 1
type: Views
title: Table
---

A table displays rows data.

## When to use

- To display a collections of structured data.
- To sort, search, paging, filter data.

## How to use

Sepecify `dataSource` of Table to be an array data.

```jsx
const dataSource = [{
  key: '1',
  name: 'Mike',
  age: 32,
  address: '10 Downing Street'
}, {
  key: '2',
  name: 'John',
  age: 42,
  address: '10 Downing Street'
}];

const columns = [{
  title: 'Name',
  dataIndex: 'name',
  key: 'name',
}, {
  title: 'Age',
  dataIndex: 'age',
  key: 'age',
}, {
  title: 'Address',
  dataIndex: 'address',
  key: 'address',
}];

<Table dataSource={dataSource} columns={columns} />
```

## API

### Table

| Property      | Type                     | Default         | Description  |
|---------------|--------------------------|-----------------|--------------|
| rowSelection  | 列表项是否可选择，[配置项](#rowSelection) | Object  | null  |
| pagination    | 分页器，配置项参考 [pagination](/components/pagination)，设为 false 时不显示分页 | Object |  |
| size          | 正常或迷你类型，`default` or `small`  | String | default |
| dataSource    | 数据数组 | Array |            |
| columns       | 表格列的配置描述，具体项见下表 | Array | - |
| rowKey        | 表格行 key 的取值，可以是字符串或一个函数 | String or Function(record, index):string | 'key' |
| rowClassName  | 表格行的类名      | Function(record, index):string | - |
| expandedRowRender  | 额外的展开行 | Function | - |
| defaultExpandedRowKeys | 默认展开的行 | Array | - |
| expandedRowKeys | 展开的行，控制属性 | Array | - |
| onChange      | 分页、排序、筛选变化时触发 | Function(pagination, filters, sorter) |  |
| loading       | 页面是否加载中 | Boolean | false |
| locale        | 默认文案设置，目前包括排序、过滤、空数据文案 | Object | filterConfirm: '确定' <br> filterReset: '重置' <br> emptyText: '暂无数据' <br> [默认值](https://github.com/ant-design/ant-design/issues/575#issuecomment-159169511) |
| indentSize    | 展示树形数据时，每层缩进的宽度，以 px 为单位 | Number   | 15 |
| onRowClick    | 处理行点击事件 | Function(record, index)   | - |
| useFixedHeader  | 是否固定表头 | Boolean | false      |
| bordered  | 是否展示外边框和列边框 | Boolean | false      |
| showHeader  | 是否显示表头 | Boolean          | true      |
| footer  | 表格底部自定义渲染函数         | Function(currentPageData)   | |
| title  | 表格头部自定义渲染函数         | Function(currentPageData)   | |
| scroll  | 横向或纵向支持滚动，也可用于指定滚动区域的宽高度：`{{ x: true, y: 300 }}` | Object   | -  |

### Column

One of Property `columns` for descriping column.

| Property      | Type                     | Default         | Description  |
|---------------|--------------------------|-----------------|--------------|
| title      | 列头显示文字               | String or React.Element | - |
| key        | React 需要的 key，建议设置 | String          | - |
| dataIndex  | 列数据在数据项中对应的 key，支持 `a.b.c` 的嵌套写法 | String | - |
| render     | 生成复杂数据的渲染函数，参数分别为当前行的值，当前行数据，行索引，@return里面可以设置表格[行/列合并](#demo-colspan-rowspan) | Function(text, record, index) {} | - |
| filters    | 表头的筛选菜单项           | Array           | - |
| onFilter   | 本地模式下，确定筛选的运行函数 | Function    | - |
| filterMultiple | 是否多选 | Boolean    | true    |
| filterDropdown | 可以自定义筛选菜单，此函数只负责渲染图层，需要自行编写各种交互 | React.Element | - |
| sorter     | 排序函数，本地排序使用一个函数，需要服务端排序可设为 true | Function or Boolean | - |
| colSpan    | 表头列合并,设置为 0 时，不渲染 | Number      |         |
| width      | 列宽度 | String or Number | -  |
| className  | 列的 className             | String          |  -      |
| fixed      | 列是否固定，可选 `true`(等效于 left) `'left'` `'right'` | Boolean or String | false |
| filteredValue | 筛选的受控属性，外界可用此控制列的筛选状态，值为已筛选的 value 数组 | Array | - |
| sortOrder | 排序的受控属性，外界可用此控制列的排序，可设置为 `'ascend'` `'descend'` `false` | Boolean or String | - |

### rowSelection

Properties for selection.

| Property      | Type                     | Default         | Description  |
|---------------|--------------------------|-----------------|--------------|
| type | 多选/单选，`checkbox` or `radio` | String | `checkbox`  |
| selectedRowKeys | 指定选中项的 key 数组，需要和 onChange 进行配合 | Array | []  |
| onChange | 选中项发生变化的时的回调 | Function(selectedRowKeys, selectedRows) | -   |
| getCheckboxProps | 选择框的默认属性配置        | Function(record) |  -   |
| onSelect | 用户手动选择/取消选择某列的回调         | Function(record, selected, selectedRows) |   -   |
| onSelectAll | 用户手动选择/取消选择所有列的回调    | Function(selected, selectedRows, changeRows) |   -   |

## Note

According to [React documentation](http://facebook.github.io/react/docs/multiple-components.html#dynamic-children), every child in array should be assigned a unique key. The value inside `dataSource` and `columns` should follow this in Table, and `dataSource[i].key` would be treated as key value defaultly for `dataSource`.

If `dataSource[i].key` is not existed, then you should specify the primary key of dataSource value via `rowKey`. If not, warnings like above will show in browser console.

![](https://os.alipayobjects.com/rmsportal/luLdLvhPOiRpyss.png)

```jsx
// primary key is uid
return <Table rowKey="uid" />;
// or
return <Table rowKey={record => record.uid} />;
```
