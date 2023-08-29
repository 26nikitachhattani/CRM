<template>
  <div>
    <div class="mb-3 title-text">New Post</div>
    <v-sheet color="my-3 py-5 px-3 info-sheet">
      Your content will need to be approved by a moderator
    </v-sheet>
    <div>
      <v-alert
        v-model="alert"
        dismissible
        color="white"
        elevation="0 "
        icon="mdi-bell"
      >
        Forums Forum is a peer-to-peer community for anyone building their
        website and online business.
      </v-alert>
    </div>
    <v-form ref="form">
      <v-card height="700">
        <v-card-text class="my-3">
          <div class="my-2 sub-header">Title <span>Required</span></div>
          <v-text-field
            v-model="title"
            label="Title"
            class="mt-1"
            :rules="[rules.required]"
            outlined
          ></v-text-field>
          <div class="my-2 sub-header">Tags <span>Required</span></div>
          <v-combobox
            v-model="select"
            label="Tag"
            outlined
            prepend-inner-icon="mdi-plus"
            multiple
            :rules="[rules.requiredArray]"
            :items="items"
            :search-input.sync="search"
            hide-selected
            hint="Maximum of 5 tags"
            persistent-hint
            small-chips
          >
            <template v-slot:no-data>
              <v-list-item>
                <v-list-item-content>
                  <v-list-item-title>
                    No results matching "<strong>{{ search }}</strong
                    >". Press <kbd>enter</kbd> to create a new one
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </template>
          </v-combobox>
          <div class="my-1 sub-header">Discussion <span>Required</span></div>
          <quillEditor
            hide-details
            :rules="[rules.required]"
            v-model="description"
            id="editor-container"
          />
        </v-card-text>
        <v-card-actions class="px-7 my-10">
          <v-btn outlined dark class="submit-btn primary" rounded text to="/">
            Close
          </v-btn>
          <v-spacer></v-spacer>
          <v-btn
            outlined
            dark
            class="submit-btn primary"
            rounded
            text
            @click="submit"
          >
            Submit Topic
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-form>
    <v-snackbar
      v-model="snackbar"
      color="red"
    >
      {{ text }}

      <template v-slot:action="{ attrs }">
        <v-btn
          
          text
          v-bind="attrs"
          @click="snackbar = false"
        >
          Close
        </v-btn>
      </template>
    </v-snackbar>
  </div>
</template>

<script>
//import QuillEditor from "./common/QuillEditor.vue";
import { quillEditor } from "vue-quill-editor";
import "quill/dist/quill.snow.css";
export default {
  data: () => ({
    items: ["Gaming", "Programming", "Vue", "Vuetify"],
    model: ["Vuetify"],
    search: null,
    alert: true,
    title: "",
    tag: "",
    description: "",
    topics: [],
    date: new Date().toLocaleDateString(),
    rules: {
      required: (value) => !!value || "Required.",
      requiredArray: (value) => !!value.length || "Required.",
    },
     snackbar: false,
    text: `please fill data`,
  }),
  watch: {
    model(val) {
      if (val.length > 5) {
        this.$nextTick(() => this.model.pop());
      }
    },
  },
  methods: {
    submit() {
      if(this.$refs.form.validate() && this.description.length !== 0){
      if (localStorage.getItem("topics") !== null) {
        this.topics = JSON.parse(localStorage.getItem("topics"));
      } else {
        this.topics = []; // Initialize topics as an empty array if it doesn't exist in localStorage
      }

      this.topics.push({
        title: this.title,
        tag: this.select,
        description: this.description,
        date: this.date,
      });

      // Save the updated topics array back to localStorage
      localStorage.setItem("topics", JSON.stringify(this.topics));
      this.$router.push("/");
      }
      else{
        this.snackbar = true
      }
    },
  },
  components: {
    quillEditor,
    //quillEditor,
  },
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap");
.info-sheet {
  background: #e5e5e5 0% 0% no-repeat padding-box;
  border: 1px solid #dddddd;
  border-radius: 5px;
  opacity: 1;
  color: #b72828;
  font: normal normal bold 17px/23px Open Sans;
  letter-spacing: 0px;
}
.title-text {
  font: normal normal 600 24px Open Sans;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
.sub-header {
  text-align: left;
  font: normal normal 600 13px Open Sans;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
.sub-header > span {
  text-align: left;
  font: normal normal 600 10px/14px Open Sans;
  letter-spacing: 0px;
  color: #b72828;
  text-transform: uppercase;
  opacity: 1;
}
.submit-btn {
  background: #2991ea 0% 0% no-repeat padding-box;
  border-radius: 5px;
  opacity: 1;
  text-transform: capitalize;
}
</style>
