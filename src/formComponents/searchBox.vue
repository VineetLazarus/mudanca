<template>
<div>
    <div class="control-section">
        <div id='content' style="margin: 0px auto; width:300px; padding-top: 10px;">
            <ejs-autocomplete id='employees' :dataSource='data' :fields='fields' :placeholder='watermark' @close="onSearchClose"
             :headerTemplate="'hTemplate'" :itemTemplate="'iTemplate'" popupHeight="450px" cssClass='autocomplete-template'>
              <template v-slot:hTemplate="{}">
                <!--<div class="header"> <span>Image</span> <span class="info">Product Info</span></div>-->
              </template>
              <template v-slot:iTemplate="{data}">
                <div>
                    <img class="empImage" :src="require(`@/${data.Eimg}`)">
                    <div class="ename"> {{data.Name}} </div>
                    <div class="job"> {{data.Category}} </div>
                </div>
              </template>              
             </ejs-autocomplete>
        </div>
    </div>
</div>
</template>
<script>
import { AutoCompleteComponent } from "@syncfusion/ej2-vue-dropdowns";
import data from '../data/productData.json';

export default {
    components: {
        'ejs-autocomplete': AutoCompleteComponent
    },
    data: function() {
        return {
            fields: { value: 'Name' },
            rpath: '',
            watermark: 'e.g. Weekly Planner',
            data: data['products']
        };
    },
    methods: {
        onSearchClose() {
            this.$emit('onSearchClose')
        }
    }
}
</script>

<style scoped>

    .control-section {
        display: flex;
    }
    .searchIcon {
        padding-top: 20px;
        margin-right: 5px;
    }
    .autocomplete-template .header {
        font-weight: 600;
        color: rgba(0, 0, 0, .54);
        height: 48px;
        padding: 15px 0 0 16px;
        font-size: 16px;
        background-color: #f5f5f5;
    }

    .fabric .autocomplete-template .header {
        background-color: #fff;
        border-bottom: 1px solid #ccc;
        color: #0078d7;
        font-weight: 400;
    }

    .bootstrap .autocomplete-template .header {
        background-color: #fff;
        border-bottom: 1px solid #ccc;
        color: #777;
        font-weight: 400;
        font-size: 12px;
        line-height: 30px;
        height: 30px;
        padding: 0 0 0 24px;
    }

    .highcontrast .autocomplete-template .header {
        color: #fff;
        background-color: #000;
    }

    .e-bigger.bootstrap .autocomplete-template .header {
        line-height: 44px;
        height: 44px;
        font-size: 13px;
    }

    .bootstrap .autocomplete-template .info,
    .e-bigger.bootstrap .autocomplete-template .info {
        margin-left: 25px;
    }

    .bootstrap .autocomplete-template .job {
        opacity: .54;
        font-size: 14px;
        margin-top: -25px;
        margin-bottom: 20px;
    }

    .e-bigger.bootstrap .autocomplete-template .job {
        font-size: 15px;
        margin-top: -32px;
        margin-bottom: 17px;
    }
    
    .tailwind .autocomplete-template .job {
        margin-top: -7px;
        margin-bottom: 5px;
    }

    .e-bigger.tailwind .autocomplete-template .job {
        margin-top: -15px;
        margin-bottom: 5px;
    }


    .bootstrap .autocomplete-template .ename {
        font-size: 15px;
        margin-top: 20px;
        opacity: .87;
        padding: 3px 0 20px;
    }

    .e-bigger.bootstrap .autocomplete-template .ename {
        font-size: 16px;
        padding-bottom: 15px;
    }

    .bootstrap .autocomplete-template .empImage,
    .e-bigger.bootstrap .autocomplete-template .empImage {
        margin: 0px 10px 0 20px;
    }

    .autocomplete-template .info {
        margin-left: 17px;
    }

    .autocomplete-template .ename {
        display: block !important;
        opacity: .87;
        font-size: 16px;
        margin-top: 8px;
    }

    .autocomplete-template .job {
        opacity: .54;
        font-size: 14px;
        margin-top: -15px;
        margin-bottom: 7px;
    }

    .autocomplete-template .empImage {
        margin: 6px 16px;
        float: left;
        width: 50px;
        height: 50px;
    }

    .autocomplete-template.e-popup .e-list-item * {
        display: block;
        text-indent: 0;
    }

    .e-bigger:not(.bootstrap) .autocomplete-template .e-dropdownbase .e-list-item {
        line-height: 42px;
        height: 80px;
    }

    .e-bigger:not(.bootstrap) .autocomplete-template.e-popup .empImage {
        margin: 10px 16px;
    }
    .bootstrap4 .autocomplete-template.e-popup .empImage {
        margin: 0px 16px;
    }

    .bootstrap4 .autocomplete-template.e-popup .job {
        margin-top: 0;
    }
    .e-bigger.bootstrap4 .autocomplete-template.e-popup .job {
        margin-top: -15px;
    }
    .bootstrap4 .autocomplete-template .header {
        color: #6c757d;
    }
     .fluent-dark .header {
        background: #252423;
        color: #2899F5;
    }

    .bootstrap5-dark .autocomplete-template .header {
        background: #343A40;
        color: #7B848D;
    }

    .fluent .autocomplete-template .header{
         color: #2899F5;
    }

    .tailwind-dark .autocomplete-template .header {
        background: #374151;
        color: rgb(255, 255, 255);
    }

    .material3-dark .autocomplete-template .header,
    .material-dark .autocomplete-template .header {
        background: rgb(66, 66, 66);
        color: rgb(255, 255, 255);
    }

    .fabric-dark .autocomplete-template .header {
        background: rgb(40, 39, 39);
        color: rgb(255, 255, 255);
    }

    .bootstrap-dark .autocomplete-template .header {
        background: rgb(49, 49, 49);
        color: rgb(255, 255, 255);
    }
</style>