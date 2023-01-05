<template>
  <div class="flex items-center justify-center w-1/2" style="margin: 16px auto">
    <div class="overflow-hidden bg-white shadow sm:rounded-lg bg-indigo-300">
      <div class="px-4 py-5 sm:px-6">
        <h3 class="text-lg font-medium leading-6 text-gray-900">
          Global data
        </h3>
      </div>
      <div class="border-t border-gray-200">
        <dl>
          <div
            class="bg-gray-50 px-4 py-5 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-6"
          >
            <dt class="text-sm font-medium text-gray-500">Total cases</dt>
            <dd class="mt-1 text-sm text-gray-900 sm:col-span-2 sm:mt-0">
                {{ getFormattedNumber(stats.TotalConfirmed) }}
            </dd>
          </div>
          <div
            class="bg-white px-4 py-5 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-6"
          >
            <dt class="text-sm font-medium text-gray-500">New Cases</dt>
            <dd class="mt-1 text-sm text-gray-900 sm:col-span-2 sm:mt-0">
              {{ getFormattedNumber(stats.NewConfirmed) }}
            </dd>
          </div>
        </dl>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "DataBox",
  props: ['stats'],
  methods:{
    getFormattedNumber(numner){
        return String(numner).replace(/(.)(?=(\d{3})+$)/g,'$1,')
    }
  }
};
</script>
