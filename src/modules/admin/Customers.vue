<template>
  <sidebar>
    <div>
      <div>
        <p
          style="color: purple;font-weight: bold;font-family: Segoe Script;font-style: italic;font-size: 20px;margin-top: 1%;"
        >Customer's Management</p>
      </div>
      <table
        class="table table-purple"
        style="font-size: 15px;-align: center;margin-bottom: 1rem;width: 40%;"
      >
        <thead>
          <tr>
            <th
              scope="col"
              style="padding: 8px;color: white;background-color: blueviolet;width: 10%;border: 2px solid violet;"
            >SORT</th>
            <th class="dropdown text-center" style="background-color: violet;color:purple;border: 2px solid violet;">
              <a
                data-toggle="dropdown"
                class="dropdown-toggle"
                aria-haspopup="true"
                aria-expanded="false"
              >Total Orders</a>
              <ul class="dropdown-menu">
                <li>
                  <a class="dropdown-item">Completed Orders</a>
                  <a class="dropdown-item">Cancelled Orders</a>
                  <a class="dropdown-item">Best Buyers</a>
                </li>
              </ul>
            </th>
          </tr>
        </thead>
      </table>
      <b-form-input class="searchbar" placeholder="Search here..."></b-form-input>
        <div>
          <b-table class="table table-bordered text-center" :items="items" :fields="fields" style="border: 2px solid violet;">
            <template v-slot:cell(ACTIONS)>
              <i
                class="fa fa-eye"
                data-toggle="modal"
                data-target="#ViewHistory"
                style="font-size:20px;"
                aria-hidden="true"
              ></i>
            </template>
          </b-table>
        <!-- History Modal -->
        <div
          class="modal fade bd-example-modal-lg"
          id="ViewHistory"
          tabindex="-1"
          role="dialog"
          aria-labelledby="CustomerHistoryModal"
          aria-hidden="true"
        >
          <div class="modal-dialog modal-lg" role="document">
            <!-- ModalComponent -->
            <CustomerTransactionHistory/>
          </div>
        </div>
      </div>
    </div>
  </sidebar>
</template>
<script>
// import CustomerModal from "../basic/Customer_Modal";
import sidebar from "../../components/frame/sidebar";
export default {
  components: {
    sidebar,
    // CustomerModal
  },
  data() {
    return {
      fields: [
        "USERNAME",
        "TOTAL_ORDERS",
        "COMPLETED_ORDERS",
        " CANCELLED_ORDERS",
        "ACTIONS"
      ],
      items: [
        {
          USERNAME: "mingming",
          TOTAL_ORDERS: "",
          COMPLETED_ORDERS: "",
          CANCELLED_ORDERS: ""
          // ACTIONS: ""
        },
        {
          USERNAME: "mingming",
          TOTAL_ORDERS: "",
          COMPLETED_ORDERS: "",
          CANCELLED_ORDERS: ""
          // ACTIONS: ""
        }
      ]
    };
  },
  methods: {
    customerModal() {
      this.$refs.Customermodal.shown();
    }
  }
};
</script>
<style scoped>

.dropdown-toggle {
  cursor: pointer;
}
a {
  color: purple;
  text-decoration: none;
  background-color: transparent;
}
.a:hover {
  color: purple;
  text-decoration: none;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  display: none;
  width: 102%;
  font-size: 1.5rem;
  color: blueviolet;
  text-align: center;
  list-style: none;
  background-color: violet;
  margin-left: -27%;
  margin-top: 3.5%;
}
.dropdown-menu:hover {
  cursor: pointer;
  background-color: violet;
}
.form-control {
  width: 60%;
  height: calc(1.5em + 0.75rem + 2px);
  padding: 0.375rem 0.75rem;
  font-size: 20px;
  color: violet;
  background-color: #fff;
  background-clip: padding-box;
  border: 2px solid violet;
  border-radius: 0.25rem;
  float: right;
  margin-top: -5.3%;
}
.fa-eye:hover {
  cursor: pointer;
}
</style>
