<template>
  <section class="container posts-page">
    <el-card>
      <div slot="header" class="clearfix">
        <span>新規投稿</span>
      </div>
      <el-table :data="showPosts" style="width: 100%" class="table">
        <el-table-column prop="title" label="タイトル"></el-table-column>
        <el-table-column prop="user.id" label="投稿者" width="180">
        </el-table-column>
        <el-table-column
          prop="created_at"
          label="投稿日時"
          width="240"
        ></el-table-column>
      </el-table>
    </el-card>
  </section>
</template>

<script>
import faker from "faker";
export default {
  computed: {
    showPosts() {
      return [
        {
          id: "001",
          title: "title001",
          body: faker.lorem.sentence,
          created_at: "2019/07/23 12:00:00",
          user: {
            id: "mitomex"
          }
        },
        {
          id: "002",
          title: "title002",
          body: faker.lorem.sentence,
          created_at: "2019/07/24 12:00:00",
          user: {
            id: "mitomex"
          }
        }
      ];
    }
  }
};
</script>

<style>
.posts-page .el-table__row {
  cursor: pointer;
}
</style>
