var util = require('../../utils/util.js')
var moment = require('../../libs/moment.js')
const AV = require('../../libs/av-live-query-weapp-min')

Page({
   data: {
      datalists: [],
   },
   // 页面加载
   onLoad: function () {
      var that = this;

      // 批量获取
      AV.Object.fetchAll('location').then(function (objects) {
         console.log("成功！" + JSON.stringify(objects))

      }, function (error) {
         console.log("失败！" + JSON.stringify(error))
      });

      wx.request({
         url: 'https://leancloud.cn:443/1.1/classes/location',
         method: 'GET',
         data: {

         },
         header: {
            'Content-Type': 'application/json',
            'X-LC-Id': 'muOaEf1eUm1fFTGUkxoHDuXU-gzGzoHsz',
            'X-LC-Key': 'UxNkFSMvDY10sRpHBVx8uoJI'
         },
         success: function (e) {
            var datajson = e.data.results;
            var data0 = datajson[0].createdAt;

            console.log("日期：" + moment("12-25-1995", "MM-DD-YYYY"))

            that.setData({
               datalists: datajson
            })
         },
         fail: function (e) {
            console.log(JSON.stringify(e.data));
         }
      })
   }

})