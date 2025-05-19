<script setup lang="ts">
import data from "~/assets/archiv.json";

const tableData = Object.entries(data).map(([rok, items]) => ({
  rok,
  items,
}));

const search = ref("");

const filteredData = computed(() => {
  if (!tableData) {
    return [];
  }

  if (!search.value) {
    return tableData;
  }

  const term = search.value.toLowerCase();

  return tableData
    .map(({ rok, items }) => ({
      rok,
      items: items.filter(
        (item: any) =>
          (item.meno && item.meno.toLowerCase().includes(term)) ||
          (item.praca && item.praca.toLowerCase().includes(term)) ||
          (item.odbor && item.odbor.toLowerCase().includes(term)) ||
          (item.umiestnenie && item.umiestnenie.toLowerCase().includes(term))
      ),
    }))
    .filter((group) => group.items.length > 0);
});
</script>

<template>
  <div class="archiv">
    <h2>Archív prác</h2>
    <input v-model="search" type="text" placeholder="Hľadajte" />
    <div class="grid-rokov">
      <div v-if="filteredData.length > 0">
        <div v-for="group in filteredData" :key="group.rok" class="skolsky-rok">
          <h3>{{ group.rok }}</h3>
          <ul>
            <li v-for="(item, i) in group.items" :key="i">
              <h4>
                <span>{{ item.meno }}</span>
                {{ item.praca }}
                <i>{{ item.odbor }}</i>
              </h4>
              <p>{{ item.umiestnenie }}</p>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.archiv {
  justify-content: center;
  flex-direction: column;
  padding: 0 20px 35px;
  background-color: #f4f4f4;
  border-top: #e0e0e0 2px solid;
  border-bottom: #e0e0e0 2px solid;
}

.archiv input {
  padding: 6px 10px;
  font-size: 16px;
  max-width: 400px;
  width: 100%;
  border-radius: 10px;
  box-sizing: border-box;
  display: block;
  margin: 20px auto;
}

.h2 {
  font-size: 32px;
  color: #004080;
  margin: 30px 0 30px 0;
}

.grid-rokov {
  column-count: 3;
  column-gap: 20px;
  max-width: 1200px;
  margin: 0 auto;
}

.skolsky-rok {
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  margin-bottom: 20px;
  display: inline-block;
  width: 100%;
  padding: 20px;
}

.skolsky-rok h3 {
  font-size: 22px;
  color: #004080;
  margin-bottom: 15px;
  text-align: center;
}
.skolsky-rok h4 {
  color: #3d73cf;
  text-decoration: none;
  font-weight: bold;
}

.skolsky-rok a {
  color: #3d73cf;
  text-decoration: none;
  font-weight: bold;
}

.skolsky-rok i {
  display: block;
  margin-top: 5px;
  font-size: 14px;
  color: #4c87a39c;
}

.skolsky-rok ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.skolsky-rok li {
  background: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 15px;
  margin-bottom: 15px;
}

.skolsky-rok li h4 {
  font-size: 16px;
  color: #3d73cf;
  margin-bottom: 10px;
}

.skolsky-rok li span {
  color: #1e004e9c;
}

.skolsky-rok li p {
  font-size: 14px;
  color: #555;
  margin: 5px 0 0 0;
}

.skolsky-rok li i {
  display: block;
  font-size: 14px;
  color: #4c87a39c;
  margin-top: 5px;
}

.skolsky-rok a:hover {
  text-decoration: underline;
}

.skolsky-rok p {
  font-size: 16px;
  color: #555;
  margin: 5px 0 0 0;
  text-align: left;
}

@media (max-width: 1100px) {
  .grid-rokov {
    column-count: 2;
  }
}

@media (max-width: 620px) {
  .grid-rokov {
    column-count: 1;
  }
}
</style>
