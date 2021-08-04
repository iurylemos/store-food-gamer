<template>
  <div>
    <Header />
    <AboutCompany />
    <OurTeam />
    <Feedback />
    <Footer />
  </div>
</template>

<script>
import Header from "../components/Header";
import AboutCompany from "../components/Main/AboutCompany.vue";
import OurTeam from "../components/Main/OurTeam.vue";
import Feedback from "../components/Main/Feedback.vue";
import Footer from "../components/Main/Footer.vue";

export default {
  components: {
    Header,
    AboutCompany,
    OurTeam,
    Feedback,
    Footer
  }
};
</script>
