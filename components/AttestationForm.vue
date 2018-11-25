<template>
    <div id="AttestComponent">
      <button @click="showForm=!showForm">Launch Attestation</button>
      <br>
      <container class="pull-right" id="AttestForm" v-show="showForm">
        <form class="form-horizontal">
          <div class="form-group"><h4>Report Acknowledgement</h4></div>
          <div  class="form-group" id="supervisor">
          Supervisor : {{supervisor}}
          </div>
          <div  class="form-group" id="reporteddate">
          Reported Date : {{reportedDate}}
          </div>
          <div class="form-group">
            <div class="radio">
              <label>
                <input type="radio" id="OK" value="OK" v-model="attestType">
                OK
              </label>
            </div>
            <div class="radio">
              <label>
              <input type="radio" id="Resolved" value="UNRESOLVED" v-model="attestType">
              Caveats Unresolved
              </label>
            </div>
            <div class="radio">
              <label>
              <input type="radio" id="Unresolved" value="RESOLVED" v-model="attestType">
              Caveats Resolved
              </label>
            </div>
            <span class="form-group">Attested: {{ attestType}}</span>
          </div>
          <div class="form-group">
            <label id=lblcomm for="Comments">Comments</label>
            <input class="form-control" type="text" id="Comments" v-model="comments">
          </div>
          <div class="form-group">
            <button id="submit" @click="showForm=!showForm">Submit</button><span>     </span><button id="cancel" @click="showForm=!showForm">Cancel</button>
          </div>
        </form>
      </container>

    </div>
</template>

<script>
export default {
  name: 'AttestationForm',
  props: {
    supervisor: '',
    reportedDate: ''
  },
  data () {
    return {
      comments: '',
      showForm: false,
      attestType: ''
    }
  }
}
</script>

<style scoped>
  #AttestForm {
    width: 300px;
    height: 380px;
    background-color: rgb(247, 249, 251);
    display: block;
    text-align: left;
    padding: 40px;
    border: 2px;
    border-color: blue;
  }

 /* #AttestForm{
    width: 300px;
    height: 600px;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
    !*grid-gap: 5px;*!
    grid-template-areas:    "s s s . . ."
                            "d d d . . ."
                            ". r r r . ."
                            ". r r r . ."
                            ". r r r . ."
                            "l 1 1 . . ."
                            ". c c c c ."
                            ". c c c c ."
                            ". b1 . . b2 .";
    background-color: rgb(247, 249, 251);
    padding: 2px;
  }
  #supervisor {
    grid-area: s;
  }
  #reporteddate {
    grid-area: d;
  }
  .form-group {
    grid-area: r;
  }
  #lblcomm {
    grid-area: l;
  }
  #Comments {
    grid-area: c;
  }
  #submit {
    grid-area: b1
  }
  #cancel {
    grid-area: b2;
  }*/

</style>
