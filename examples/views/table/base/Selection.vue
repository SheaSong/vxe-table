<template>
  <div>
    <p>使用默认方式，勾选全部事件select-all，勾选事件select-change</p>

    <button class="btn" @click="$refs.xTable.toggleRowSelection(tableData[1])">切换第二行选中</button>
    <button class="btn" @click="$refs.xTable.setSelection([tableData[2], tableData[3]], true)">设置第三、四行选中</button>
    <button class="btn" @click="$refs.xTable.setSelection(tableData, true)">设置所有行选中</button>
    <button class="btn" @click="$refs.xTable.clearSelection()">清除所有行选中</button>
    <vxe-table
      ref="xTable"
      border
      height="300"
      :data.sync="tableData">
      <vxe-table-column type="selection" width="60"></vxe-table-column>
      <vxe-table-column prop="name" label="Name"></vxe-table-column>
      <vxe-table-column prop="sex" label="Sex"></vxe-table-column>
      <vxe-table-column prop="age" label="Age"></vxe-table-column>
      <vxe-table-column prop="address" label="Address" show-overflow></vxe-table-column>
    </vxe-table>

    <p>使用 prop 绑定方式</p>

    <vxe-table
      border
      height="300"
      :data.sync="tableData">
      <vxe-table-column prop="checked" type="selection" width="60"></vxe-table-column>
      <vxe-table-column prop="name" label="Name"></vxe-table-column>
      <vxe-table-column prop="sex" label="Sex"></vxe-table-column>
      <vxe-table-column prop="age" label="Age"></vxe-table-column>
      <vxe-table-column prop="address" label="Address" show-overflow></vxe-table-column>
    </vxe-table>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: []
    }
  },
  created () {
    let list = window.MOCK_DATA_LIST.slice(0, 50)
    this.tableData = list
  }
}
</script>
