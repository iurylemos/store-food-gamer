<template>
  <div>
    <HeaderIndex />
    <AboutCompanyIndex />
    <OurTeamIndex />
    <FeedbackIndex />
    <FooterIndex />
  </div>
</template>

<script>
export default {
  data() {
    return {
      developers: [
        {
          name: "Iury Lemos",
          office: "Software Developer"
        },
        {
          name: "Venicius",
          office: "Software Developer"
        }
      ]
    };
  }
};
</script>
