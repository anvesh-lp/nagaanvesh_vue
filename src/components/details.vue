<template>
  <div>
    <h2>Doctor Name : {{ detail.doctorname }}</h2>
    <h2>Reason : {{ detail.reason }}</h2>
    <h2>patient Name : {{ detail.patientname }}</h2>
    <h2>Diagnostic date : {{ detail.diagnoseddate }}</h2>
    <h2>Hospital Name : {{ detail.hospitalname }}</h2>
    <h2>Check_in Date : {{ detail.entrydate }}</h2>
  </div>
</template>
<script>

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'details',
  props: {
    detail: JSON
  }
}
</script>

<style scoped>

h4 {
  margin: 2px;
}

div {
  background-color: #fad9f5;
  border-radius: 50px;
  color: black;
  padding: 1em;
}

.red {
  background-color: #f3eae7 !important;

}

</style>