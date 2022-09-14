<template>
  <div>
    <div class="main">
      <div class="header">
        <p>Card Details</p>
      </div>
      <div class="content">
        <table width="100%">
          <tr>
            <th width="15%">Name</th>
            <td width="5%">:</td>
            <td width="80%">{{ name }}</td>
          </tr>
          <tr>
            <th width="15%">Age</th>
            <td width="5%">:</td>
            <td width="80%">{{ age }}</td>
          </tr>
          <tr>
            <th width="15%">Department</th>
            <td width="5%">:</td>
            <td width="80%">{{ department }}</td>
          </tr>
          <tr>
            <th width="15%">Skill</th>
            <td width="5%">:</td>
            <td width="80%">{{ skill }}</td>
          </tr>
        </table>

        <button class="button">Add To Cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["name", "age", "department", "skill"],
  data() {
    return {};
  },
};
</script>

<style>
.main {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  max-width: 300px;
  margin: auto;
  text-align: center;
  font-family: arial;
}
.header p {
  padding: 5px;
  margin: 0;
  background: rgb(41, 6, 73);
  color: #fff;
}
.content {
  padding: 10px;
  text-align: left;
  min-height: 120px;
}
.button {
  border: none;
  outline: 0;
  padding: 5px;
  color: white;
  background-color: rgb(2, 75, 18);
  text-align: center;
  cursor: pointer;
  width: 100%;

  margin-top: 50px;
  font-size: 14px;
  left: 10px;
  bottom: 5px;
  right: 10px;
}
</style>
