<template>
  <!-- tabbeer -->
  <div>
    <div id="tabs" class="container">
      <div class="tabs">
        <a
          v-on:click="activetab = '1'"
          v-bind:class="[activetab === '1' ? 'active' : '']"
          >General</a
        >
        <a
          v-on:click="activetab = '2'"
          v-bind:class="[activetab === '2' ? 'active' : '']"
          >Identity</a
        >
        <a
          v-on:click="activetab = '3'"
          v-bind:class="[activetab === '3' ? 'active' : '']"
          >Clinic
        </a>
        <a
          v-on:click="activetab = '4'"
          v-bind:class="[activetab === '4' ? 'active' : '']"
          >Security Roles</a
        >
      </div>

      <div class="content">
        <div v-if="activetab === '1'" class="tabcontent d-flex">
          <div class="me-5"></div>
          <div class="ms-5">
            <datatable></datatable>
          </div>
        </div>

        <div v-if="activetab === '2'" class="tabcontent">
          <table>
            <tr>
              <td class="legend">Area:</td>
              <td class="data">505,990 km<sup>2</sup></td>
              <td rowspan="5">
                <img
                  class="map"
                  src="https://drive.google.com/thumbnail?id=1AlVDaA3-wXNhqtXkfWoI3tD5cxZNfJu1"
                />
              </td>
            </tr>
            <tr>
              <td class="legend">Population:</td>
              <td class="data">47 million</td>
            </tr>
            <tr>
              <td class="legend">Capital:</td>
              <td class="data">Madrid</td>
            </tr>
            <tr>
              <td class="legend">Language:</td>
              <td class="data">Spanish</td>
            </tr>
            <tr>
              <td class="legend" valign="top">Flag:</td>
              <td class="data">
                <img
                  class="flag"
                  src="https://upload.wikimedia.org/wikipedia/en/thumb/9/9a/Flag_of_Spain.svg/750px-Flag_of_Spain.svg.png"
                  width="80"
                />
              </td>
            </tr>
          </table>
        </div>
        <div v-if="activetab === '3'" class="tabcontent">
          <table>
            <tr>
              <td rowspan="5">
                <NestedExample :data="clinicData"></NestedExample>
              </td>
            </tr>
          </table>
        </div>
        <div v-if="activetab === '4'" class="tabcontent">
          <table>
            <tr>
              <td class="dataRoot" rowspan="5">
                <NestedExample :data="rootData"></NestedExample>
              </td>
            </tr>

            <tr>
              <td class="legend" valign="top"></td>
              <td class="rightAdmincontent">
                <div class="ms-5">
                  <h5>admin.users</h5>
                  <h5>Allowed permission definitions</h5>

                  <div class="card" style="width: 18rem">
                    <div class="card-body">
                      <div class="form-check">
                        <input
                          class="form-check-input"
                          type="checkbox"
                          value=""
                          id="flexCheckDefault"
                        />
                        <label class="form-check-label" for="flexCheckDefault">
                          Default checkbox
                        </label>
                      </div>
                      <div class="form-check">
                        <input
                          class="form-check-input"
                          type="checkbox"
                          value=""
                          id="flexCheckDefault"
                        />
                        <label class="form-check-label" for="flexCheckDefault"
                          >Default checkbox</label
                        >
                      </div>
                      <div class="form-check">
                        <input
                          class="form-check-input"
                          type="checkbox"
                          value=""
                          id="flexCheckDefault"
                        />
                        <label class="form-check-label" for="flexCheckDefault">
                          Default checkbox
                        </label>
                      </div>
                    </div>
                  </div>
                </div>
              </td>
            </tr>
          </table>
        </div>
      </div>
    </div>
  </div>
  <!-- <div ><TabberComponent v-if="TabberComponent.contents" /></div> -->
</template>

<script>
import NestedExample from "./NestedExample.vue";
import datatable from "./DataTable.vue";
import root from "@/root.json";

export default {
  name: "AllTabs",
  components: {
    NestedExample,
    datatable,
  },
  data() {
    return {
      rootData: root,
      // nodes: ["a","l"],
      activetab: "1",
      flag: 2,
      clinicData: clinics,
    };
  },
  methods: {
    func() {
      if (this.flag > 0) {
        this.flag--;
      } else {
        return false;
      }
    },
  },
  beforeMount() {
    this.func();
  },
};
</script>

<style scoped>
/* Import Google Font */
@import url(https://fonts.googleapis.com/css?family=Nunito+Sans);

/* RESET */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.container {
  max-width: 920px;
  min-width: 420px;
  margin: 40px auto;
  font-family: "Nunito Sans", Arial, Helvetica, sans-serif;
  font-size: 0.9em;
  color: #888;
}

/* Style the tabs */
.tabs {
  overflow: hidden;
  margin-bottom: -2px; /* hide bottom border */
  margin-left: 24px;
}
a {
  text-decoration: none;
  color: #aaa;
}

.tabs a {
  float: left;
  cursor: pointer;
  padding: 12px 24px;
  transition: background-color 0.2s;
  border: 1px solid #ccc;
  border-right: none;
  background-color: #f1f1f1;
  border-radius: 10px 10px 0 0;
  font-weight: bold;
}
.tabs a:last-child {
  border-right: 1px solid #ccc;
}

/* Change background color of tabs on hover */
.tabs a:hover {
  background-color: #aaa;
  color: #fff;
}

/* Styling for active tab */
.tabs a.active {
  background-color: #fff;
  color: #484848;
  border-bottom: 2px solid #fff;
  cursor: default;
}

/* Style the tab content */
.tabcontent {
  padding: 30px 50px;
  border: 1px solid #ccc;
  border-radius: 10px;
  box-sizing: border-box;
  box-shadow: 4px 4px 8px #e1e1e1;
}

.tabcontent td {
  padding: 0.3em 0.4em;
  color: #484848;
}
.tabcontent td.dataRoot {
  max-width: 30rem;
  text-align: left;
}
.tabcontent td.legend {
  color: #888;
  font-weight: bold;
  text-align: right;
}
ul[data-v-4037d787] {
  padding-left: 0;
}
.tabcontent .map {
  height: 173px;
  width: 220px;
  background: #d3eafb;
  margin-left: 60px;
  border: 1px solid #ccc;
  border-radius: 10px;
}
.data {
  width: 120px;
}
</style>
