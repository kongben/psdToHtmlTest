<template>
  <div class="select_item">
    <span class="title">{{name}}:</span>
    <select name="" id="" class="select_list">
        <option value="1" disabled selected style='display:none;'>{{select_placeholder}}</option>
        <option value="1">2</option>
        <option value="1">3</option>
    </select>
  </div>
</template>

<script>
export default {
 props:{
     name:String,
     select_placeholder:String
 }
};
</script>

<style scoped>
.select_item{
    margin-bottom: 5px;
}
.title {
  font-size: 14px;
  font-family: "Microsoft YaHei";
  color: rgb(111, 150, 169);
  line-height: 1.714;
}
.select_list {
  border-width: 1px;
  border-color: rgb(252, 250, 243);
  border-style: solid;
  background-color: rgb(88, 128, 148);
  width: 122px;
  height: 23px;
  z-index: 184;
   font-size: 12px;
  font-family: "Microsoft YaHei";
  color: rgb(252, 250, 243);
  line-height: 2;
}


</style>
