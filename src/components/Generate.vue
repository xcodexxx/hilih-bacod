<template>
    <div class="container my-5 text-center justify-content-center">
        <div class="row">
            <div class="col-md-12">
                <h3>
                    Bacod Generator
                </h3>
                <h5>
                    {{ description }}
                </h5>
                <h4>
                    by <a target="_blank" href="https://instagram.com/ricez_">Ric Ez</a>
                </h4>
            </div>
        </div>

        <div class="row justify-content-center">
            <div class="col-md-6">
                <div class="form-group">
                    <textarea placeholder="halah" v-model="bacod" cols="30" rows="2" class="form-control" style="font-size: 30px;"></textarea>
                </div>
            </div>
        </div>

        <div class="row justify-content-center mb-4">
            <div class="col-md-6">
                <button @click="changeType('bacod', 'Convert (a, u, e, o) => i')" v-bind:class="[type === 'bacod' ? 'btn-primary' : 'btn-outline-primary']" class="btn mx-1 font-weight-bold" style="letter-spacing: 2px;">
                    hilih
                </button>
                <button @click="changeType('byksw', 'bahasa para byksw')" v-bind:class="[type === 'byksw' ? 'btn-primary' : 'btn-outline-primary']" class="btn mx-1 font-weight-bold" style="letter-spacing: 2px;">
                    Byksw
                </button>
            </div>
        </div>

        <div class="row justify-content-center" style="font-size: 30px;">
            <div class="col-md-6">
                <div class="card">
                    <div class="card-header text-center">
                        <div>Hasil Generate</div>
                        <button data-clipboard-target="#bacod" class="btn btn-outline-success btn-sm font-weight-bold">
                            Copy / Salin
                        </button>
                    </div>
                    <!-- <div class="form-group card-body"> -->
                        <textarea placeholder="hilih" id="bacod" v-model="this.generated" cols="30" rows="2" class="form-control" style="font-size: 30px;"></textarea>
                    <!-- </div> -->
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            type: 'bacod', 
            description: 'Convert (a, u, e, o) => i', 
            bacod: ''
        }
    }, 
    methods: {
        changeType(type, description){
            this.type = type
            this.description = description
        }
    },
    computed: {
        generated(){
            let res
            switch (this.type) {
                case 'bacod':
                    res = this.bacod.replace(/a|i|u|e|o/gi, 'i');
                    break;
                case 'byksw':
                    res = 
                    this.bacod
                    .replace(/i/gi, 'y')
                    .replace(/e/gi, 'w')
                    .replace(/o/gi, 'w')
                    .replace(/a/gi, 'w')
                    .replace(/u/gi, 'w')
                    break;
                default:
                    res = this.bacod.replace(/a|i|u|e|o/gi, 'i');
                    break;
            }
            return res
        }
    }
}   
</script>

<style lang="scss">
    
</style>