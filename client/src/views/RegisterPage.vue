<script>
import { mapActions } from "pinia";
import { useAppStore } from "../stores/appStore";
export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    ...mapActions(useAppStore, ["doRegister"]),
    // =======================
    handleRegister() {
      this.doRegister({
        username: this.username,
        email: this.email,
        password: this.password,
      });
    },
  },
  created() {},
};
</script>

<template>
  <!-- Register Section -->
  <section class="vh-95" style="background-image: url(https://img.theculturetrip.com/wp-content/uploads/2016/10/hk-nights-03304.jpg)" id="register-section">
    <div class="container py-5 h-95">
      <div class="row d-flex justify-content-center align-items-center h-95 my-3">
        <div class="col col-xl-10">
          <div class="card" style="border-radius: 1rem">
            <div class="row g-1">
              <div class="col-md-5 col-lg-4 d-none d-md-block me-3">
                <img src="https://i.pinimg.com/564x/bd/07/21/bd072104d552b01127a6e5334b0d4171.jpg" alt="login form" class="img-fluid" style="border-radius: 1rem 0 0 1rem" />
              </div>
              <div class="col-md-6 col-lg-7 d-flex align-items-center">
                <div class="card-body p-2 p-lg-1 text-black">
                  <!-- <img src="../assets/ppua.jpeg" alt="" style="width: 200px; height: 200px" /> -->
                  <form id="register-form" @submit.prevent="handleRegister">
                    <h5 class="fw-normal mb-3 pb-3" style="letter-spacing: 1px">Register for your account</h5>

                    <div class="form-outline mb-1">
                      <input v-model="username" id="register-username" type="text" class="form-control form-control-lg required" />
                      <label class="form-label" for="form2Example27">Username</label>
                    </div>

                    <div class="form-outline mb-1">
                      <input v-model="email" id="register-email" type="email" class="form-control form-control-lg" />
                      <label class="form-label">Email address</label>
                    </div>

                    <div class="form-outline mb-1">
                      <input v-model="password" id="register-password" type="password" class="form-control form-control-lg" />
                      <label class="form-label" for="form2Example27">Password</label>
                    </div>

                    <div class="pt-1 mb-2">
                      <button class="btn btn-dark btn-lg btn-block" type="submit" style="width: 100%">Register</button>
                    </div>

                    <p @click.prevent="$router.push('/login')" class="mb-1 pb-lg-1" style="color: #393f81">Already have an account? <a id="register-link" href="" style="color: #393f81">Login here</a></p>
                  </form>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- End Register Section -->
</template>

<style></style>
