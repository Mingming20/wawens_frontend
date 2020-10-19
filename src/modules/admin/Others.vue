<template>
  <div>
    <sidebar>
      <b-container class="mt-5">
        <div>
          <p class="d-flex justify-content-between pothers">
            Others
            <!-- Testtimonial AddButton -->
            <button
              data-toggle="modal"
              data-target="#AddTestimonial"
              type="button"
              id="addbutton"
              v-show="categories[0].show"
              class="btn btn-light"
              aria-hidden="true"
            >+ Add Testimonial</button>
            <!-- Partner AddButton -->
            <button
              data-toggle="modal"
              data-target="#AddDistributor"
              type="button"
              id="addbutton"
              v-show="categories[1].show && index == 0"
              class="btn btn-light"
            >+ Add Distributor</button>
            <button
              data-toggle="modal"
              data-target="#AddReseller"
              type="button"
              id="addbutton"
              v-show="categories[1].show && index == 1"
              class="btn btn-light"
            >+ Add Reseller</button>
            <!-- FAQ AddButton -->
            <button
              data-toggle="modal"
              data-target="#AddFaqs"
              type="button"
              id="addbutton"
              v-show="categories[2].show"
              class="btn btn-light"
            >+ Add FAQ</button>
          </p>
          <!--Testimonial Modal-->
          <div
            class="modal fade bd-example-modal-lg"
            id="AddTestimonial"
            tabindex="-1"
            role="dialog"
            aria-labelledby="TestimonialModal"
            aria-hidden="true"
          >
            <div class="modal-dialog modal-lg" role="document">
              <div class="modal-content">
                <div class="modal-header">
                  <h5
                    class="modal-title"
                    style="font-size: 20px;color: purple;margin-left: 35%;"
                  >ADD NEW TESTIMONY</h5>
                  <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                  </button>
                </div>
                <div class="modal-body">
                  <b-container class="testimonial-modal mb-3">
                    <b-row class="font-weight-bold" cols="2">
                      <b-col style="font-size: 15px;">Name:</b-col>
                      <b-col style="font-size: 15px;">Photo:</b-col>
                    </b-row>
                  </b-container>
                  <div class="row">
                    <b-form-input class="nameinput"></b-form-input>
                    <b-form-group class="upload1" label-for="file-default" label-cols-sm="2">
                      <br>
                      <b-form-file browse-text="Upload File" placeholder="Choose File" class="file" id="file-default"></b-form-file>
                    </b-form-group>
                  </div>
                  <label for="labelanswer">Comment:</label>
                  <b-form-textarea rows="8" style="font-size: 10px;"></b-form-textarea>
                </div>
                <div class="modal-footer">
                  <button
                    id="bclose"
                    type="button"
                    class="btn btn-secondary"
                    data-dismiss="modal"
                  >CANCEL</button>
                  <button
                    type="button"
                    class="btn btn-primary"
                    data-toggle="modal"
                    data-target=".bd-example-modal-lg"
                    style="width: 20%;color: white;background-color: purple;"
                  >SUBMIT</button>
                </div>
              </div>
            </div>
          </div>
          <!--Testimonial End-->
          <!-- Distributor Modal -->
          <div
            class="modal fade"
            id="AddDistributor"
            tabindex="-1"
            role="dialog"
            aria-labelledby="PartnerModal"
            aria-hidden="true"
          >
            <div class="modal-dialog modal-dialog-centered" role="document">
              <div class="modal-content">
                <div class="modal-header">
                  <h5
                    class="modal-title"
                    style="font-size: 20px;color: purple;margin-left: 27%;"
                  >ADD NEW DISTRIBUTOR</h5>
                  <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                  </button>
                </div>
                <div class="modal-body">
                  <b-form-group
                    class="upload"
                    label="Upload:"
                    label-for="file-default"
                    label-cols-sm="2"
                  >
                    <br>
                    <b-form-file placeholder="Choose File" browse-text="Upload File" class="file" id="file-default"></b-form-file>
                  </b-form-group>
                </div>
                <div class="modal-footer">
                  <button
                    id="bclose"
                    type="button"
                    class="btn btn-secondary"
                    data-dismiss="modal"
                  >CANCEL</button>
                  <button
                    type="button"
                    class="btn btn-primary"
                    style="width: 20%;color: white;background-color: purple;"
                  >ADD</button>
                </div>
              </div>
            </div>
          </div>
          <!-- Distributor End -->
          <!-- Reseller Modal -->
          <div
            class="modal fade"
            id="AddReseller"
            tabindex="-1"
            role="dialog"
            aria-labelledby="PartnerModal"
            aria-hidden="true"
          >
            <div class="modal-dialog modal-dialog-centered" role="document">
              <div class="modal-content">
                <div class="modal-header">
                  <h5
                    class="modal-title"
                    style="font-size: 20px;color: purple;margin-left: 27%;"
                  >ADD NEW RESELLER</h5>
                  <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                  </button>
                </div>
                <div class="modal-body">
                  <b-form-group
                    class="upload"
                    label="Upload:"
                    label-for="file-default"
                    label-cols-sm="2"
                  >
                    <br>
                    <b-form-file browse-text="Upload File" placeholder="Choose File" class="file" id="file-default"></b-form-file>
                  </b-form-group>
                </div>
                <div class="modal-footer">
                  <button
                    id="bclose"
                    type="button"
                    class="btn btn-secondary"
                    data-dismiss="modal"
                  >CANCEL</button>
                  <button
                    type="button"
                    class="btn btn-primary"
                    style="width: 20%;color: white;background-color: purple;"
                  >ADD</button>
                </div>
              </div>
            </div>
          </div>
          <!-- Reseller End -->
          <!-- FAQ Modal -->
          <div
            class="modal fade bd-example-modal-lg"
            id="AddFaqs"
            tabindex="-1"
            role="dialog"
            aria-labelledby="FAQModal"
            aria-hidden="true"
          >
            <div class="modal-dialog modal-lg" role="document">
              <div class="modal-content">
                <div class="modal-header">
                  <h5
                    class="modal-title"
                    style="font-size: 20px;color: purple;margin-left: 28%;"
                  >ADD FREQUENTLY ASKED QUESTIONS</h5>
                  <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                  </button>
                </div>
                <div class="modal-body">
                  <label for="labelquestion">Question:</label>
                  <b-form-textarea rows="8" style="font-size: 10px;"></b-form-textarea>
                  <label for="labelanswer">Answer:</label>
                  <b-form-textarea rows="8" style="font-size: 10px;"></b-form-textarea>
                </div>
                <div class="modal-footer">
                  <button
                    id="bclose"
                    type="button"
                    class="btn btn-secondary"
                    data-dismiss="modal"
                  >CANCEL</button>
                  <button
                    type="button"
                    class="btn btn-primary"
                    style="width: 20%;color: white;background-color: purple;"
                  >SUBMIT</button>
                </div>
              </div>
            </div>
          </div>
          <!-- FAQ End -->
        </div>
        <table class="table table-purple" style="text-align: center;">
          <thead>
            <tr>
              <th class="thtable1" @click="showCategoryInfo('testimonial')">TESTIMONIALs</th>
              <th class="thtable" @click="showCategoryInfo('partner')" scope="col">PARTNERs</th>
              <th class="thtable" @click="showCategoryInfo('faqs')" scope="col">FAQs</th>
            </tr>
          </thead>
        </table>
        <div class="component" style="margin-top: -6%;">
          <Testimonial v-show="categories[0].show"></Testimonial>
          <Partner v-show="categories[1].show" @changeTab="changeTab"></Partner>
          <FAQ v-show="categories[2].show"></FAQ>
        </div>
      </b-container>
    </sidebar>
  </div>
</template>
<script>
import Testimonial from "@/modules/others/Testimonial.vue";
import Partner from "@/modules/others/Partner.vue";
import FAQ from "@/modules/others/FAQs.vue";
import sidebar from "../../components/frame/sidebar";
export default {
  components: {
    sidebar,
    Testimonial,
    Partner,
    FAQ
  },
  data: () => ({
    testimonial: true,
    partner: false,
    faqs: false,
    categories: [
      { name: "testimonial", show: true },
      { name: "partner", show: false },
      { name: "faqs", show: false }
    ],
    index: 0
  }),
  methods: {
    showCategoryInfo(category) {
      this.categories.forEach(component => {
        if (component.name == category) {
          component.show = true;
        } else {
          component.show = false;
        }
      });
    },
    changeTab(index) {
      this.index = index;
    }
  }
};
</script>

<style scoped>
.nameinput {
  font-size: 15px;
  width: 40%;
  margin-left: 3%;
}
label {
  font-size: 15px;
}
.upload {
  font-size: 15px;
}
.upload1 {
  font-size: 15px;
  margin-left: 6%;
  margin-top: -4%;
}
.file {
  height: calc(1.5em + 0.75rem + 2px);
  padding: 0.375rem 0.75rem;
  line-height: 1.5;
  color: #495057;
  background-color: #fff;
  border: 1px solid #ced4da;
  border-radius: 0.25rem;
  margin-top: 3%;
  margin-left: -15%;
}
#bclose {
  width: 20%;
  color: purple;
  background-color: white;
}
.thtable1 {
  width: 30%;
  padding: 8px;
  color: purple;
  border: 2px solid violet;
  font-size: 20px;
}
.thtable:hover {
  text-decoration: underline;
  cursor: pointer;
}
.thtable1:hover {
  text-decoration: underline;
  cursor: pointer;
}
.thtable {
  padding: 8px;
  color: purple;
  border: 2px solid violet;
  font-size: 20px;
}
#addbutton {
  width: 25%;
  background-color: blueviolet;
  color: white;
  margin-top: -0.5%;
  font-family: Arial, Helvetica, sans-serif;
  font-weight: bold;
}
.p1 {
  font-size: 12px;
  font-style: italic;
  color: purple;
  font-weight: bold;
}
table,
td {
  border: 2px solid violet;
  border-collapse: collapse;
  text-align: center;
  font-weight: bold;
}
.pothers {
  color: purple;
  font-weight: bold;
  font-family: Segoe Script;
  font-style: italic;
  margin-top: -2%;
  font-size: 20px;
}
</style>
