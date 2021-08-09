 <template>
  <div class="page">
    <div v-if="page">
      <!-- <label for="title">Title</label>
      <input
        type="text"
        v-model="page.title"
        class="title"
        name="title"
        placeholder="Enter a title"
      /> -->
      <label for="content"></label>
      <textarea
        class="note"
        name="note"
        v-model="page.note"
        placeholder="Enter some note"
      ></textarea>
      <button @click="deleteNote()">Delete Note</button>
      <button @click="saveNote()">Save Note</button>
    </div>
    <div v-else>
      <h1>&larr; To start, create a new page!</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "Page",
  props: ["page"],
  methods: {
    deleteNote() {
      this.$emit("delete-note");
    },
    saveNote() {
      this.$emit("save-note");
    },
  },
};
</script>

<style scoped>
.page {
  width: 100%;
  padding: 4rem;
  box-shadow: 3rem 0 5rem 3rem #c1f5ff;
}

.note {
  border-style: none;
  border-radius: 0.25rem;
  border: solid 1px lightgray;
  width: 100%;
  box-sizing: border-box;
  margin-bottom: 1.25rem;
}

.note:focus {
  outline: 0;
}

.note {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  resize: vertical;
  font-size: 1.5rem;
  padding: 0.5rem;
  height: 20rem;
}

label {
  margin-bottom: 0.5rem;
  display: inline-block;
}

button {
  border-style: none;
  padding: 0.5rem 0.75rem;
  background-color: #44abc3;
  margin-right: 1rem;
  border-radius: 0.25rem;
  color: white;
  font-size: 1rem;
  cursor: pointer;
}

button:hover {
  background-color: #368ea2;
}
</style>
	