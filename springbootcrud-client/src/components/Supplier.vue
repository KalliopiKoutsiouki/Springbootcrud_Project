<template>
  <el-dialog :close-on-click-modal="false" :close-on-press-escape="false" :modal="true" :modal-append-to-body="false"
             :show-close="false"
             :visible="visible" @close="clearValidation" title="Διαχείριση Προμηθευτή" type="warning"
             width="75%">

    <el-card>
      <el-form :model="supplier" :rules="rules" label-position="top" ref="supplierForm">

        <el-row :gutter="20">
          <!-- LEFT COLUMN -->
          <el-col :span="12">

            <el-form-item label="Εισάγετε το Όνομα της Εταιρίας"
                          prop="companyName">
              <el-input autoComplete="name"
                        placeholder="Όνομα"
                        prefix-icon="fa fa-user"
                        v-model="supplier.companyName">
              </el-input>

            </el-form-item>
            <el-form-item label="Εισάγετε το Όνομα"
                          prop="firstName">
              <el-input autoComplete="name"
                        placeholder="Όνομα"
                        prefix-icon="fa fa-user"
                        v-model="supplier.firstName">
              </el-input>
            </el-form-item>
            <el-form-item label="Εισάγετε το Επώνυμο"
                          prop="lastName">
              <el-input autoComplete="name"
                        placeholder="Όνομα"
                        prefix-icon="fa fa-user"
                        v-model="supplier.lastName">
              </el-input>
            </el-form-item>

            <el-form-item label="Εισάγετε ΑΦΜ"
                          prop="vatNumber">
              <el-input autoComplete="vat"
                        placeholder="ΑΦΜ"
                        prefix-icon="fa fa-phone"
                        v-model="supplier.vatNumber">
              </el-input>
            </el-form-item>

            <el-form-item label="Εισάγετε τη Δ.Ο.Υ."
                          prop="irsOffice">
              <el-input autoComplete="ΔΟΥ"
                        placeholder="Δ.Ο.Υ."
                        prefix-icon="fa fa-envelope"
                        v-model="supplier.irsOffice">
              </el-input>
            </el-form-item>
            <el-form-item label="Εισάγετε την Οδό"
                          prop="address">
              <el-input autoComplete="address"
                        placeholder="address"
                        prefix-icon="fa fa-envelope"
                        v-model="supplier.address">
              </el-input>
            </el-form-item>
            <el-form-item label="Εισάγετε Ταχυδρομικό Κωδικό"
                          prop="zipCode">
              <el-input autoComplete="ΤΚ"
                        placeholder="Τ.Κ."
                        prefix-icon="fa fa-envelope"
                        v-model="supplier.zipCode">
              </el-input>
            </el-form-item>
            <el-form-item label="Εισάγετε την Πόλη"
                          prop="city">
              <el-input autoComplete="city"
                        placeholder="Πόλη"
                        prefix-icon="fa fa-envelope"
                        v-model="supplier.city">
              </el-input>
            </el-form-item>
            <el-form-item label="Εισάγετε την Χώρα"
                          prop="country">
              <el-input autoComplete="country"
                        placeholder="Χώρα"
                        prefix-icon="fa fa-envelope"
                        v-model="supplier.country">
              </el-input>
            </el-form-item>

          </el-col>

        </el-row>

      </el-form>

      <el-row>
        <el-col style="text-align: right">
          <el-button @click="save"
                     icon="fa fa-save"
                     type="success"> Αποθήκευση
          </el-button>

          <el-button :disabled="!isDeletable"
                     @click="confirmDelete"
                     icon="fa fa-remove"
                     type="danger"> Διαγραφή
          </el-button>
        </el-col>
      </el-row>
    </el-card>

    <div class="dialog-footer card-footer" slot="footer">
      <el-button @click="cancel"
                 icon="el-icon-back"
                 type="warning"> Επιστροφή
      </el-button>
    </div>

  </el-dialog>
</template>
<script src="./SupplierVM.js"></script>

