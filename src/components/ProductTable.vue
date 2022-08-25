<template>
  <div class="bigtable">

    <div class="tile is-parent">
      <h1 class="title is-8 ">Lens List Compare Room</h1>
    </div>
    <div class="blank">

 
    </div>

    <div class="buttons">
      <button v-if="!filterOn" class="button is-light" @click="selectedObj.length>1 ? filterOn = true: filterOn = false">Compare</button>
      <button v-if="filterOn" class="button is-dark" @click="filterOff">Clean</button>
    </div>

    <table class="table is-striped is-fullwidth $table-background-color">
      <thead>
        <tr>
          <th><abbr title="Compare"></abbr></th>
          <th>Name</th>
          <th><abbr title="Model">Model</abbr></th>
          <th><abbr title="Provider">Provider</abbr></th>
          <th><abbr title="Diameter">φD(mm)</abbr></th>
          <th><abbr title="Focal Length">f(mm)</abbr></th>
          <th><abbr title="Center Thickness">tc(mm)</abbr></th>
          <th><abbr title="Edge Thickness">te(mm)</abbr></th>
          <th><abbr title="Radius of Curva">r(mm)</abbr></th>
          <th><abbr title="Availability">Avail</abbr></th>
          <th>Price</th>
        </tr>
      </thead>
      <tfoot>
        <tr>
          <th><abbr title="Compare"></abbr></th>
          <th>Name</th>
          <th><abbr title="Model">Model</abbr></th>
          <th><abbr title="Provider">Provider</abbr></th>
          <th><abbr title="Diameter">φD(mm)</abbr></th>
          <th><abbr title="Focal Length">f(mm)</abbr></th>
          <th><abbr title="Center Thickness">tc(mm)</abbr></th>
          <th><abbr title="Edge Thickness">te(mm)</abbr></th>
          <th><abbr title="Radius of Curva">r(mm)</abbr></th>
          <th><abbr title="Availability">Avail</abbr></th>
          <th>Price</th>
        </tr>
      </tfoot>

      <tbody v-if="!filterOn">
        <tr v-for="lens in json" :key="lens.model" class="">
          <th>
            <label class="checkbox">
              <input type="checkbox"  @click="pickLens($event)" :id="lens.model" :checked="lens.checked">
            </label>
          </th>
          <td><a href="" title="Leicester City F.C.">{{lens.name}}</a></td>
          <td>{{lens.model}}</td>
          <td>{{lens.provider}}</td>
          <td>{{lens.diameter}}</td>
          <td>{{lens.focal_length}}</td>
          <td>{{lens.center_thickness}}</td>
          <td>{{lens.edge_thickness}}</td>
          <td>{{lens.radius_of_curvature}}</td>
          <td>{{lens.availability}}</td>
          <td>{{lens.price}}</td>
        </tr>
      </tbody>

        <tbody v-if="filterOn">
        <tr v-for="lens in selectedObj" :key="lens.model" class="">
          <th>
          </th>
          <td><a href="">{{lens.name}}</a></td>
          <td>{{lens.model}}</td>
          <td>{{lens.provider}}</td>
          <td>{{lens.diameter}}</td>
          <td>{{lens.focal_length}}</td>
          <td>{{lens.center_thickness}}</td>
          <td>{{lens.edge_thickness}}</td>
          <td>{{lens.radius_of_curvature}}</td>
          <td>{{lens.availability}}</td>
          <td>{{lens.price}}</td>
        </tr>
      </tbody>

    </table>

    <div class="buttons">
      <button v-if="!filterOn" class="button is-light" @click="selectedObj.length>1 ? filterOn = true: filterOn = false">Compare</button>
      <button v-if="filterOn" class="button is-dark" @click="filterOff">Clean</button>
    </div>
  </div>
</template>

<script>
import JsonList from '../assets/lenses.json'
export default {
  name: 'ProductTable',
  data() {
      return {
          json: Object.values(JsonList),
          selectedLens: [],
          selectedObj: [],
          filterOn: false
      };
  },
  methods: {
    pickLens(event) {
      if (event.target.checked) {
        this.selectedObj.push(JsonList[event.target.id])
      } else {
        for (let obj of this.selectedObj) {
          if (obj.model === event.target.id) {
            const i = this.selectedObj.indexOf(obj)
            this.selectedObj.splice(i, 1)
          }
        }
      }
    },
    filterOff() {
      this.filterOn = false
      this.selectedObj = []
    }
  }
}
</script>


<style scoped>
.bigtable {
  width: 80%;
  margin: 60px auto 60px !important;
}
.blank{
  height: 40px;
}
</style>