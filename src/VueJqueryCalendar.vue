<template>
    <div>
        <input :value="value" type="text" class="datepicker" :readonly="{'readonly': readonly}" :class="className" ref="vueJqueryCalender">
    </div>
</template>
<script>
import $ from 'jquery';
import 'jquery-ui-dist/jquery-ui';

export default {
    name: 'VueJqueryCalendar',
    props: {
        value: {
            type: String,
            default: null
        },
        showButtonPanel: {
            type: Boolean,
            default: false
        },
        changeMonth: {
            type: Boolean,
            default: false
        },
        changeYear: {
            type: Boolean,
            default: false
        },
        numberOfMonths: {
            type: Number,
            default: 1
        },
        dateFormat: {
            type: String,
            default: 'dd/mm/yy'
        },
        readonly: {
            type: Boolean,
            default: false
        },
        className: {
            type: String,
            default: null
        },
    },
    mounted() {
        var that = this;
        $(this.$refs.vueJqueryCalender).datepicker({
            'showButtonPanel': this.showButtonPanel,
            'changeMonth': this.changeMonth,
            'changeYear': this.changeYear,
            'numberOfMonths': this.numberOfMonths,
            'dateFormat': this.dateFormat,
            onSelect: function() {
                that.$emit('input', this.value)
                that.$emit('change', this.value)
            }
        });
    },
}
</script>