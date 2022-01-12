<template>
    <div class="row block-transfer">
        <div class="d-flex">
            <div style="flex-grow: 1">
            <h4 class="mb-3">Danh sach chuyen cho ngoi tang xx</h4>
            </div>
            <div>
            <a @click="$emit('outTransfer')"><i class="fa fa-remove"></i></a>
            </div>
        </div>
        <div class="d-flex list-transfer">
            <div class="row" style="width: 100%; margin: auto;">
            <div class="col-sm-5" style="padding: 0 6px;">
                <div class="py-2">
                    <div class="d-flex justify-content-center transfer-table"
                        v-for="transferBlock in transferBlocks[0]"
                        :key="transferBlock.id"
                    >
                        <div class="number-table" style="width: 100%">
                        <p>Ban so {{transferBlock.seat_id}}</p>
                        <p class="m-name">Trang thai:</p>
                        <p>Trống</p>
                        </div>
                        <div style="margin-top: 2.5em">
                        <button type="button" class="btn btn-outline-dark bt-transfer" 
                            data-toggle="modal"
                            data-target="#mdtransfer">
                            Chuyen
                        </button>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-sm-7" style="padding: 0 6px;">
                <div class="py-2">
                    <div class="d-flex justify-content-center transfer-table"
                        v-for="transferBlock in transferBlockBs[0]"
                        :key="transferBlock.id"
                    >
                        <div class="number-table" style="width: 100%">
                        <p>Ban so {{transferBlock.seat_id}}</p>
                        <p class="m-name">Ten: {{transferBlock.employees.name}}</p>
                        <p>Trang thai: ton tai</p>
                        </div>
                        <div style="margin-top: 2.5em">
                        <button type="button" @click="newSeatId = transferBlock.seat_id" class="btn btn-outline-dark bt-transfer" data-toggle="modal"
                            data-target="#mdtransfer">
                            Chuyen
                        </button>
                        </div>
                    </div>
                </div>
                <div class="py-2">
                    <div class="d-flex justify-content-center transfer-table"
                        v-for="transferBlock in transferBlockBs[1]"
                        :key="transferBlock.id"
                    >
                        <div class="number-table" style="width: 100%">
                        <p style="background: #1a2a3cb8; color: white">Ban so {{transferBlock.seat_id}}</p>
                        <p class="m-name">Ten: {{transferBlock.employees.name}}</p>
                        <p style="background: #1a2a3cb8; color: white;">Trang thai: ton tai</p>
                        </div>
                        <div style="margin-top: 2.5em">
                        <button type="button" @click="newSeatId = transferBlock.seat_id" class="btn btn-dark bt-transfer" disabled>
                            Chuyen
                        </button>
                        </div>
                    </div>
                </div>
            </div>
            </div>
        </div>
        </div>
        <!-- modal transfer seat ---------------------------------------------------------------------------- -->
        <div
        class="modal fade"
        id="mdtransfer"
        tabindex="-1"
        role="dialog"
        aria-labelledby="checkTransfer"
        aria-hidden="true"
        >
        <div class="modal-dialog" role="document">
            <div
            class="modal-content"
            style="width: 60%; margin: 130px auto"
            >
            <div class="modal-body">
                <div class="row">
                <h3 class="mb-4">Thong bao</h3>
                <p class="mt-4">Ban co muon chuyen doi cho ngoi khong?</p>
                </div>
            </div>
            <div class="modal-footer" style="padding: 0">
                <div
                class="col-sm-6"
                style="border-right: 1px solid #dee2e6; padding: 1em 0"
                >
                <a @click="$emit('update', newSeatId)" class="message-del">YES</a>
                </div>
                <div class="col-sm-6" style="padding: 1em 0">
                <a class="message-del" data-dismiss="modal" aria-label="Close">
                    No
                </a>
                </div>
            </div>
            </div>
        </div>
    </div>

</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
        transferBlocks: [],
        transferBlockBs: [],
        newSeatId: '',
        };
    },
    async created () {
     const transferBlock = await axios.get('http://localhost:8080/v2/e2bf1d7a/listseat')
          this.transferBlocks = transferBlock.data.data
          this.transferBlockBs = transferBlock.data.data[1]
          console.log(2222, this.transferBlocks);
    },
    emit: ['outTransfer']
}
</script>

<style scoped>
.block-transfer {
  border: 2px solid;
  padding: 15px;
  position: fixed;
  display: block;
  width: 28%;
}
.list-transfer {
  height: 380px;
  overflow-y: scroll;
  border: 2px solid;
}
.transfer-table {
  height: 120px;
  margin: 15px 0;
}
.transfer-table p {
  height: 30px;
  padding: 6px 4px;
  margin: 0;
  line-height: 20px;
  font-size: 11px;
}
.transfer-table .m-name {
  height: 58px;
}
.number-table {
  border: 1px solid;
  margin-right: 6px;
  line-height: 18px;
  font-weight: bolder;
  text-align: center;
}
.bt-transfer {
  width: 40px;
  height: 40px;
  font-size: 10px;
  padding: 0;
}
</style>