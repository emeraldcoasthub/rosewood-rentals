<template>
  <section class="container">
    <b-row class="mt-5" align-h="center">
      <b-col cols="12" md="8">
        <p class="text-center">
          <a href="https://rosewoodrealtyinc.com">Back to the main site</a>
        </p>
        <h1 class="text-center">Rental Application</h1>
        <h3 class="text-center">
          $50 <strong>non-refundable</strong> fee per person. Each applicant
          must make 3 times the rent.
        </h3>
        <b-form
          name="application"
          method="POST"
          data-netlify="true"
          action="/success"
          class="my-3"
          data-netlify-honeypot="bot-field"
        >
          <input type="hidden" name="form-name" value="application" />

          <h2>Personal information</h2>
          <b-row>
            <b-col cols="8">
              <b-form-group label="Property applying for">
                <b-form-input
                  type="text"
                  name="property_applying_for"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Rent">
                <b-input-group prepend="$">
                  <b-form-input type="text" name="rent" required></b-form-input>
                </b-input-group>
              </b-form-group>
            </b-col>
          </b-row>
          <b-form-group label="Full name" description="Last, First and MI">
            <b-form-input type="text" name="full_name" required></b-form-input>
          </b-form-group>
          <b-row>
            <b-col cols="6">
              <b-form-group label="Social security #">
                <b-form-input
                  v-mask="'###-##-####'"
                  v-model="social"
                  type="text"
                  name="social"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="6">
              <b-form-group label="Birth date">
                <b-form-input
                  type="date"
                  name="birthday"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="4">
              <b-form-group label="Cell phone">
                <b-form-input
                  v-mask="'(###) ###-####'"
                  v-model="cell"
                  type="tel"
                  name="cell_phone"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Home phone">
                <b-form-input
                  v-mask="'(###) ###-####'"
                  v-model="home"
                  type="tel"
                  name="home_phone"
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Work phone">
                <b-form-input
                  v-mask="'(###) ###-####'"
                  v-model="work"
                  type="tel"
                  name="work_phone"
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-form-group label="Email">
            <b-form-input type="email" name="email"></b-form-input>
          </b-form-group>
          <b-row>
            <b-col cols="8">
              <b-form-group label="Driver's license #">
                <b-form-input type="text" name="dl_num" required></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="State of issue">
                <b-form-input
                  type="text"
                  name="dl_state"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <h2>Rental history</h2>
          <b-row>
            <b-col cols="8">
              <b-form-group label="Current address">
                <b-form-input
                  type="text"
                  name="current_address"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="How long?">
                <b-form-input
                  type="text"
                  name="lived_at_current_address_for"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="6">
              <b-form-group label="City">
                <b-form-input
                  type="text"
                  name="current_address_city"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="3">
              <b-form-group label="State">
                <b-form-input
                  type="text"
                  name="current_address_state"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="3">
              <b-form-group label="Zip code">
                <b-form-input
                  v-mask="'#####'"
                  v-model="zip"
                  name="current_address_zip"
                  type="text"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="8">
              <b-form-group label="Name of landlord">
                <b-form-input
                  type="text"
                  name="current_landlord"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Landlord phone #">
                <b-form-input
                  v-mask="'(###) ###-####'"
                  v-model="currentLandlordPhone"
                  type="tel"
                  name="current_landlord_phone"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-form-group label="Prior Address">
            <b-form-input
              type="text"
              name="previous_address"
              required
            ></b-form-input>
          </b-form-group>
          <b-row>
            <b-col cols="6">
              <b-form-group label="City">
                <b-form-input
                  type="text"
                  name="previous_city"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="3">
              <b-form-group label="State">
                <b-form-input
                  type="text"
                  name="previous_state"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="3">
              <b-form-group label="Zip code">
                <b-form-input
                  type="text"
                  name="previous_zip"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="8">
              <b-form-group label="Name of prior landlord">
                <b-form-input
                  type="text"
                  name="previous_landlord"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Landlord phone #">
                <b-form-input
                  v-mask="'(###) ###-####'"
                  v-model="previousLandlordPhone"
                  type="tel"
                  name="previous_landlord_phone"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <h2>Employment history</h2>
          <b-row>
            <b-col cols="8">
              <b-form-group label="Current employer">
                <b-form-input
                  type="text"
                  name="current_employer"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Position">
                <b-form-input
                  type="text"
                  name="current_position"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="8">
              <b-form-group label="Supervisor name">
                <b-form-input
                  type="text"
                  name="current_supervisor_name"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Supervisor phone #">
                <b-form-input
                  v-mask="'(###) ###-####'"
                  v-model="supervisorPhone"
                  name="current_supervisor_name"
                  type="text"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="4">
              <b-form-group label="How long?">
                <b-form-input
                  type="text"
                  name="current_job_length"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Monthly income">
                <b-input-group prepend="$">
                  <b-form-input
                    type="text"
                    name="current_job_monthly_income"
                    required
                  ></b-form-input>
                </b-input-group>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="If military, provide rank">
                <b-form-input type="text" name="military_rank"></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="8">
              <b-form-group label="Previous employer">
                <b-form-input
                  type="text"
                  name="previous_employer"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="How long?">
                <b-form-input
                  type="text"
                  name="previous_employer_length"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <h2>Other occupantcy information</h2>
          <b-row>
            <b-col cols="6">
              <b-form-group label="# of adults">
                <b-form-input type="text" name="adults" required></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="6">
              <b-form-group label="# of children">
                <b-form-input
                  type="text"
                  name="children"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="2">
              <b-form-group label="# of pets">
                <b-form-input type="text" name="pets" required></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="5">
              <b-form-group label="Breed">
                <b-form-input type="text" name="breed" required></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="5">
              <b-form-group label="Weight">
                <b-form-input
                  type="text"
                  name="weight_of_pets"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <p>
            <strong
              >Please provide documentation for service animals prior to
              move-in.</strong
            >
          </p>
          <b-form-group label="Name of bank">
            <b-form-input type="text" name="bank_name" required></b-form-input>
          </b-form-group>
          <b-row>
            <b-col cols="8">
              <b-form-group label="Bank address">
                <b-form-input
                  type="text"
                  name="bank_address"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Bank phone #">
                <b-form-input
                  v-mask="'(###) ###-####'"
                  v-model="bankPhone"
                  type="text"
                  name="bank_phone"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="4">
              <b-form-group label="# of vehicles owned">
                <b-form-input
                  type="text"
                  name="vehicles"
                  required
                ></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Make">
                <b-form-input type="text" name="make" required></b-form-input>
              </b-form-group>
            </b-col>
            <b-col cols="4">
              <b-form-group label="Model">
                <b-form-input type="text" name="model" required></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="6">
              <b-form-group label="Have you ever filed for bankruptcy?">
                <b-form-select name="bankruptcy" required>
                  <option value="null">Please select an option</option>
                  <option value="yes">Yes</option>
                  <option value="no">No</option>
                </b-form-select>
              </b-form-group>
            </b-col>
            <b-col cols="6">
              <b-form-group
                label="If yes, what date did you file for bankruptcy?"
              >
                <b-form-input type="date" name="bankruptcy_date"></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="6">
              <b-form-group
                label="Have you ever been served an eviction notice?"
              >
                <b-form-select name="eviction" required>
                  <option value="null">Please select an option</option>
                  <option value="yes">Yes</option>
                  <option value="no">No</option>
                </b-form-select>
              </b-form-group>
            </b-col>
            <b-col cols="6">
              <b-form-group
                label="If yes, what date were you served the eviction notice?"
              >
                <b-form-input type="date" name="eviction_date"></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-form-group
            label="Haver you ever willfully or intentionally refused to pay rent?"
          >
            <b-form-select required name="refused_to_pay_rent">
              <option value="null">Please select an option</option>
              <option value="yes">Yes</option>
              <option value="no">No</option>
            </b-form-select>
          </b-form-group>
          <b-row>
            <b-col cols="6">
              <b-form-group
                label='Have you ever been convicted of a felony or pled "no contest" to any crime?'
                description="Criminal records must contain no convictions for felonies within the
                past 7 years involving the manufacture or distribution of controlled
                substances. For other felony convictions, we will conduct
                individualized assessments that take into account mitigating
                factors, such as facts & circumstances surrounding the criminal
                conduct, evidence of good tenancy before and after conduct, nature &
                severity of conviction and the amount of time that has passed since
                the conviction. Criminal history which indicates that an applicant’s
                tenancy would constitute a direct threat to the health or safety of
                other individuals or whose tenancy could result in substantial
                physical damage to the property of the owner or others may result in
                rejection of the application."
              >
                <b-form-select required name="felony">
                  <option value="null">Please select an option</option>
                  <option value="yes">Yes</option>
                  <option value="no">No</option>
                </b-form-select>
              </b-form-group>
            </b-col>
            <b-col cols="6">
              <b-form-group
                label='If yes, what date were convicted or did you plead "no contest"'
              >
                <b-form-input type="date" name="felony_date"></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-form-group label="Have you ever been involved in a lawsuit?">
            <b-form-select name="involved_in_lawsuit" required>
              <option value="null">Please select an option</option>
              <option value="yes">Yes</option>
              <option value="no">No</option>
            </b-form-select>
          </b-form-group>
          <b-form-group label="Do you smoke?">
            <b-form-select name="smoke" required>
              <option value="null">Please select an option</option>
              <option value="yes">Yes</option>
              <option value="no">No</option>
            </b-form-select>
          </b-form-group>
          <p>
            <strong>DISCLOSURE</strong> I/WE,
            <strong
              >THE UNDERSIGNED UNDERSTAND THAT ROSEWOOD REALTY, INC. IS THE
              LEASING AGENT</strong
            >
            AND REPRESENTATIVE OF THE OWNER/LANDLORD AND THAT THE LEASING AGENT
            FEES WILL BE PAID BY THE OWNER/LANDLORD. THE UNDERSIGNED
            ACKNOWLEDGES THAT THIS WRITTEN NOTICE WAS RECEIVED PRIOR TO THE
            UNDERSIGNED RECEIVING A LEASE AGREEMENT.
          </p>
          <p>
            <strong>RENTER’S INSURANCE:</strong> PROOF OF RENTER’S INSURANCE
            WILL BE required WITHIN FIVE (5) DAYS OF LEASE SIGNING!
          </p>
          <p>
            <strong>RADON GAS:</strong> NOTICE TO PROSPECTIVE TENANT: RADON IS A
            NATURALLY OCCURRING RADIOACTIVE GAS THAT, WHEN IT HAS ACCUMULATED IN
            A BUILDING IN SUFFICIENT QUANTITIES, MAY PRESENT HEALTH RISKS TO
            PERSONS WHO ARE EXPOSED TO IT OVER TIME. LEVELS OF RADON THAT EXCEED
            FEDERAL AND STATE GUIDELINES HAVE BEEN FOUND IN BUILDINGS IN THIS
            STATE. ADDITIONAL INFORMATION REGARDING RADON AND RADON TESTING MAY
            BE OBTAINED FROM YOUR COUNTY PUBLIC HEALTH UNIT.
          </p>
          <p>
            <strong>AUTHORIZATION:</strong> I HEREBY AUTHORIZE PROPERTY MANAGER,
            TO VERIFY ALL INFORMATION CONTAINED ON THIS APPLICATION, AND CONDUCT
            A FULL BACKGROUND CHECK INCLUDING, BUT NOT LIMITED TO CREDIT, BANK
            ACCOUNT, EMPLOYMENT, EVICTION, CRIMINAL BACKGROUND CHECKS, AND
            AUTHORIZE PROPERTY MANAGER TO CONTACT ANY PERSONS OR COMPANIES
            LISTED ON THIS APPLICATION.
          </p>
          <p>
            <strong>CORRECT INFORMATION:</strong> I AFFIRM THAT ALL THE
            INFORMATION ON THIS APPLICATION IS TRUE, ACCURATE, AND COMPLETE AND
            HEREBY AGREE THAT IF THIS IS NOT SO, MY APPLICATION MAY BE DENIED
            AND/OR MY LEASE MAY BE HELD IN DEFAULT AND I MAY BE SUBJECT TO
            EVICTION.
          </p>
          <p>
            <strong>LEAD BASED PAINT:</strong> HOUSING BUILT BEFORE 1978 MAY
            CONTAIN LEAD BASED PAINT. LEAD FROM PAINT, PAINT CHIPS, AND DUST CAN
            POSE HEALTH HAZARDS IF NOT MANAGED PROPERLY. LEAD EXPOSURE IS
            ESPECIALLY HARMFUL TO YOUNG CHILDREN AND PREGNANT WOMEN. BEFORE
            RENTING PRE-1978 HOUSING, LESSORS MUST DISCLOSE THE PRESENCE OF LEAD
            BASED PAINT, AND/OR LEAD BASED PAINT HAZARDS IN THE DWELLING.
            LEESEES MUST ALSO RECEIVE A FEDERALLY APPROVED PAMPHLET ON LEAD
            BASED POISONING PREVENTION. LEAD BASED HOUSING ADDENDUM WILL BE
            INCLUDED WITH LEASE FOR ALL HOUSING BUILT PRIOR TO 1978.
          </p>
          <p>
            <strong>SEXUAL OFFENDER DISCLOSURE:</strong> THE FLORIDA DEPARTMENT
            OF LAW ENFORCEMENT(FDLE) MAINTAINS A LIST OF SEXUAL
            PREDATORS/OFFENDERS TO ENABLE THE PUBLIC TO REQUEST INFORMATION
            ABOUT THESE INDIVIDUALS WHO MAY BE LIVING IN THEIR COMMUNITIES. IF
            THIS IS IMPORTANT TO YOU, CONTACT FDLE DIRECTLY PRIOR TO ENTERING
            INTO A CONTRACT AT 1-800-357-7332 (TOLL FREE), VIA E-MAIL AT
            SEXPRED@FDLE.STATE.FL.US, OR LOG ON TO WWW.FDLE.STATE.FL.US.
          </p>
          <p>
            NON REFUNDABLE LEASE APPLICATION FEE: $50.00 EACH APPLICANT, TO BE
            PAID WITH APPLICATION.
          </p>
          <p>
            <strong>SECURITY DEPOSIT:</strong> I HEREBY DEPOSIT THE SUM OF
            $__________WITH MANAGEMENT AS A SECURITY DEPOSIT. IF I DO NOT CANCEL
            THIS APPLICATION WITHIN 24 HOURS FROM THE DATE AND TIME OF THIS
            APPLICATION, IN WRITING, AND BY HAND DELIVERY TO THE RENTAL OFFICE,
            AND MY APPLICATION IS APPROVED, AND I FAIL TO ENTER INTO THE RENTAL
            AGREEMENT, OR FAIL TO TAKE POSSESSION BY COMMENCEMENT DATE AND UNDER
            THE TERMS OF THE RENTAL AGREEMENT, I UNDERSTAND THAT THE ENTIRE
            SECURITY DEPOSIT SHALL BE FORFEITED BY ME. IF I HAVE CANCELLED THIS
            APPLICATION WITHIN THE TIME PERIOD SET FORTH ABOVE, I WILL RECEIVE A
            REFUND OF MY SECURITY DEPOSIT IN FULL WITHIN 30 DAYS.
          </p>
          <b-form-group
            label="Your signature"
            description="By signing you agree to all of the conditions as written. You also agree that this signature will be legally binding as allowed by the ESIGN act."
          >
            <b-form-input type="text" name="signature" required></b-form-input>
          </b-form-group>
          <p>
            Effective October 1, 2000, The Electronic Signatures in Global and
            National Commerce Act states that electronic signatures are widely
            recognized as legally binding. "[A] signature, contract, or other
            record relating to such transaction may not be denied legal effect,
            validity, or enforceability solely because it is in electronic form;
            and (2) a contract relating to such transaction may not be denied
            legal effect, validity, or enforceability solely because an
            electronic signature or electronic record was used in its
            formation."
          </p>
          <b-btn type="submit" variant="success">Sign and Submit</b-btn>
        </b-form>
      </b-col>
    </b-row>
  </section>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      social: '',
      cell: '',
      home: '',
      work: '',
      zip: '',
      currentLandlordPhone: '',
      previousLandlordPhone: '',
      supervisorPhone: '',
      bankPhone: ''
    }
  }
}
</script>
