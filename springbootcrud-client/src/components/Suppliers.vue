<template>
  <div class="wrapper">
    <div class="animated fadeIn">
      <div class="row">
        <div class="col-lg-12">
          <el-card>
            <div slot="header">
              <i class='icon-people'></i> Προμηθευτές
            </div>
            <el-row>
              <el-col :span="5">
                <el-input
                  autoComplete="companyName"
                  placeholder="Search"
                  v-model="query">
                </el-input>
              </el-col>
              <el-col :span="0.2">
                <div class="grid-content bg-purple">&nbsp;</div>
              </el-col>
              <el-col :span="12">
                <el-button
                  @click="refreshSuppliers()"
                  class="el-button--primary">Search
                </el-button>
              </el-col>
            </el-row>
            <el-table
              :data="suppliers"
              @selection-change="onSupplierSelected"
              stripe
              style="width: 100%">
              <el-table-column
                :label="field.title"
                :prop="field.name"
                :sortable="true"
                v-bind:key="index"
                v-for="(field, index) in fields">
              </el-table-column>
              <el-table-column
                label="Operations" width="100">
                <template slot-scope="scope">
                  <el-button
                    @click="onSupplierSelected(scope.row)"
                    class="el-button--warning"
                    size="mini">Edit
                  </el-button>
                </template>
              </el-table-column>
            </el-table>

            <div style="text-align: right; margin-top: 1em">
              <el-button
                @click="createSupplier"
                class="el-button--success">
                <i class="fa fa-plus"></i>
                Δημιουργία
              </el-button>
            </div>
          </el-card>
        </div>
      </div>
    </div>
    <supplier></supplier>
  </div>
</template>

<script src="./SuppliersVM.js"></script>
