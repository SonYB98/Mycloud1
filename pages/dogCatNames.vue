<template>
  <div>
    <section class="hero is-link">
      <div class="hero-body">
        <p class="title">
          <i class="fas fa-dog"></i> 강아지와
          <i class="fas fa-cat"></i> 고양이의 행동변화
        </p>
        <p class="subtile">애완동물의 행동에 따른 변화를 알아보자</p>
      </div>
    </section>
    <hr />
    <section class="columns">
      <div class="column">
        <table class="table is-striped is-hoverable is-fullwidth">
          <thead>
            <tr>
              <th>번호</th>
              <th>강아지의 행동패턴</th>
              <th>상태</th>
            </tr>
          </thead>
          <tbody>
            <template v-for="pos in tabledogStat.length">
              <tr :key="pos">
                <td>{{ pos }}</td>
                <td>{{ tabledogStat[pos - 1] }}</td>
                <td>{{ tabledogStat2[pos - 1] }}</td>
              </tr>
            </template>
          </tbody>
        </table>
      </div>
      <div class="column">
        <table class="table is-striped is-hoverable is-fullwidth">
          <thead>
            <tr>
              <th>번호</th>
              <th>고양이의 행동패턴</th>
              <th>상태</th>
            </tr>
          </thead>
          <tbody>
            <template v-for="pos in tablecatStat.length">
              <tr :key="pos">
                <td>{{ pos }}</td>
                <td>{{ tablecatStat[pos - 1] }}</td>
                <td>{{ tablecatStat2[pos - 1] }}</td>
              </tr>
            </template>
          </tbody>
        </table>
        <div class="content">
					<p class="tag is-danger">출처</p>
					<a class="button is-primary is-small" href="/dogStat.json"
						>JSON - 상태체크</a
					><br />
				</div>
      </div>
    </section>
  </div>
</template>
<script>
import catStat from "~/assets/catStat.json";
import catStat2 from "~/assets/catStat2.json";
import dogStat from "~/assets/dogStat.json";
import dogStat2 from "~/assets/dogStat2.json";

export default {
  data() {
    return {
      tabledogStat: dogStat.names,
      tabledogStat2: dogStat2.names,
      tablecatStat: catStat.names,
      tablecatStat2: catStat2.names,
    };
  },
};
</script>