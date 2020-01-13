<template>
    <div class="container my-5 text-center justify-content-center">
        <div class="row">
            <div class="col-md-12">
                <h3>
                    Bacod Generator
                </h3>
                <h5>
                    a, i, u, e, o == i
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
                        <textarea placeholder="hilih" id="bacod" v-model="this.generatedBacod" cols="30" rows="2" class="form-control" style="font-size: 30px;"></textarea>
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
            bacod: ''
        }
    }, 
    computed: {
        generatedBacod(){
            return this.bacod.replace(/a|i|u|e|o/gi, 'i')
        }
    }
}   
</script>

<style lang="scss">
    
</style>