<template>
  <div>
    {{event }}
    <h1>Create a Contract</h1>
    <form>

      <SelectGeneric
          :options="categories"
          v-model="event.category"
          label="Select a category"
      />

      <h3>Name & describe your event</h3>

      <InputGeneric
          v-model="event.title"
          label="Title"
          type="text"
      />

      <InputGeneric
          v-model="event.description"
          label="Description"
          type="text"
      />

      <h3>Where is your event?</h3>



      <InputGeneric
          v-model="event.location"
          label="Location"
          type="text"
      />

      <h3>Are pets allowed?</h3>
      <div>
        <input
            type="radio"
            v-model="event.pets"
            :value="1"
            name="pets"
        />
        <label>Yes</label>
      </div>

      <div>
        <input
            type="radio"
            v-model="event.pets"
            :value="0"
            name="pets"
        />
        <label>No</label>
      </div>

      <h3>Extras</h3>
      <div>
        <input
            type="checkbox"
            v-model="event.extras.catering"
            class="field"
        />
        <label>Catering</label>
      </div>

      <div>
        <input
            type="checkbox"
            v-model="event.extras.music"
            class="field"
        />
        <label>Live music</label>
      </div>

      <button type="submit">Submit</button>
    </form>


  </div>
</template>

<script>
import InputGeneric from "@/components/InputGeneric.vue";
import SelectGeneric from "@/components/SelectGeneric.vue";

export default {
  components: {SelectGeneric, InputGeneric},
  data () {
    return {
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community'
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      }
    }
  }
}
</script>
