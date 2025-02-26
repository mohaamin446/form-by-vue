template>
    <div class="container">
      <h1>Medically Assisted Therapy - Psychosocial Treatment Plan</h1>
      <form @submit.prevent="submitForm">
        <!-- Client Information -->
        <div class="section">
          <h2>Client Information</h2>
          <div class="form-group">
            <label>Client Name:</label>
            <input v-model="form.clientName" type="text" required />
          </div>
          <div class="form-group">
            <label>MAT ID:</label>
            <input v-model="form.matId" type="text" required />
          </div>
          <div class="form-group">
            <label>Date:</label>
            <input v-model="form.date" type="date" required />
          </div>
        </div>
  
        <!-- Stage of Treatment -->
        <div class="section">
          <h2>Stage of Treatment</h2>
          <div class="form-group">
            <select v-model="form.stageOfTreatment" required>
              <option disabled value="">Select Stage</option>
              <option value="Induction">Induction</option>
              <option value="Re-Induction">Re-Induction</option>
              <option value="Stabilization">Stabilization</option>
              <option value="Maintenance">Maintenance</option>
              <option value="Cessation">Cessation</option>
              <option value="Other">Other</option>
            </select>
          </div>
        </div>
  
        <!-- Noted Domain Problems -->
        <div class="section">
          <h2>Noted Domain Problems</h2>
          <div class="form-group checkbox-group">
            <label><input type="checkbox" v-model="form.problems" value="Drug Use" /> Drug Use</label>
            <label><input type="checkbox" v-model="form.problems" value="Psychological Health" /> Psychological Health</label>
            <label><input type="checkbox" v-model="form.problems" value="Legal Problem" /> Legal Problem</label>
            <label><input type="checkbox" v-model="form.problems" value="Physical Health" /> Physical Health</label>
            <label><input type="checkbox" v-model="form.problems" value="Social Functioning" /> Social Functioning</label>
          </div>
        </div>
  
        <!-- Psychosocial Outcomes -->
        <div class="section">
          <h2>Psychosocial Outcomes</h2>
          <div class="form-group checkbox-group">
            <label><input type="checkbox" v-model="form.outcomes" value="Reintegration" /> Reintegration</label>
            <label><input type="checkbox" v-model="form.outcomes" value="Employment" /> Employment</label>
            <label><input type="checkbox" v-model="form.outcomes" value="Stable Accommodation" /> Stable Accommodation</label>
            <label><input type="checkbox" v-model="form.outcomes" value="Legal Problems" /> Legal Problems</label>
            <label><input type="checkbox" v-model="form.outcomes" value="GBV" /> GBV</label>
            <label><input type="checkbox" v-model="form.outcomes" value="Other" /> Other</label>
          </div>
        </div>
  
        <!-- Case Summary & Intervention -->
        <div class="section">
          <h2>Case Summary & Intervention</h2>
          <div class="form-group">
            <textarea v-model="form.caseSummary" rows="5" placeholder="Write your summary here..."></textarea>
          </div>
        </div>
  
        <!-- Counselor Details -->
        <div class="section">
          <h2>Counselor Details</h2>
          <div class="form-group">
            <label>Counselor Name:</label>
            <input v-model="form.counselorName" type="text" required />
          </div>
          <div class="form-group">
            <label>Next TCA (Date):</label>
            <input v-model="form.nextTca" type="date" />
          </div>
        </div>
  
        <!-- Submit Button -->
        <button type="submit">Submit</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        form: {
          clientName: "",
          matId: "",
          date: "",
          stageOfTreatment: "",
          problems: [],
          outcomes: [],
          caseSummary: "",
          counselorName: "",
          nextTca: "",
        },
      };
    },
    methods: {
      submitForm() {
        console.log("Form submitted:", this.form);
        alert("Form submitted successfully!");
        // You can handle the form submission logic here (e.g., sending data to an API)
      },
    },
  };
  </script>
  
  <style scoped>
  .container {
    max-width: 600px;
    margin: auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    background: #f9f9f9;
  }
  
  .section {
    margin-bottom: 20px;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  input, select, textarea {
    width: 100%;
    padding: 8px;
    margin-top: 5px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  button {
    padding: 10px 15px;
    background: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background: #0056b3;
  }
  </style>
  
