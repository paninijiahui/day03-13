<template>
  <div class="ent_form">

    <div class="form_banner">
      <img src="../assets/images/form_banner.jpg" alt="">
      <p class="form_title">【心职】扫码发布职位</p>
    </div>

    <div class="form_field">
      <p class="form_field_label">企业注册码</p>
      <input type="text" class="form_value_input" v-model="enterprisecode">
    </div>
    <div class="form_field">
      <p class="form_field_label">企业名称</p>
      <input type="text" v-model="enterprisename" class="form_value_input" placeholder="如：宁波智士网络技术有限公司">
    </div>
    <div class="form_field">
      <div class="form_field_label01">
        <p class="title_node">公司对外简称</p>
        <p class="field_note_fade">&nbsp 0/1~5</p>
      </div>
      <input type="text" v-model="shortname" class="form_value_input" placeholder="如：智士网络">
    </div>

    <hr class="line">
    <div class="form_field">
      <div class="form_field_label01">
        <p class="title_node">职位名称</p>
        <p class="field_note_fade">&nbsp 0/2~10</p>
      </div>
      <input type="text" v-model="positonname" class="form_value_input" >
    </div>

    <div class="form_field">
      <div class="form_field_label01">
        <p class="title_node">职能职业</p>
        <p class="field_note_fade">&nbsp 0/2~10</p>
      </div>
      <input type="text" v-model="skill" class="form_value_input" >
    </div>
    <div class="form_field">
      <p class="form_field_label">工作类型</p>
      <!-- <input type="text" class="form_value_input" placeholder="全职">-->
      <select name="a" id="" v-model="kinds" class="form_value_input">
        <option value="全职">全职</option>
        <option value="兼职">兼职</option>
        <option value="实习生">实习生</option>
        <option value="无固定时间">无固定时间</option>
        <option value="小时工日结">小时工日结</option>
        <option value="临时工">临时工</option>
      </select>
    </div>
    <div class="form_field">
      <div class="form_field_label01">
        <p class="title_node">招聘人数</p>
        <p class="field_note_fade">&nbsp 请输入1~1000的数字</p>
      </div>
      <!-- <input type="text" v-model.number="num" class="num_value_input" placeholder="人" >-->
      <div>
        <input type="text" v-model.number="num" class="num_value_input">
        <div id="dis" style="position: absolute;z-index:755">人</div>
      </div>
    </div>

    <div class="form_field">
      <div class="form_field_label01">
        <p class="title_node">职位描述</p>
        <p class="field_note_light">职位的详细内容和要求</p>
      </div>
      <textarea class="comments" v-model="description" placeholder="注意：要求中请勿填写涉及歧视的内容，例如：残疾，乙肝等">
     </textarea>
    </div>

    <div class="form_field">
      <div class="upload_field">
        <p class="form_field_label">工作薪资最低</p>
        <p class="salary_note_light">注：请输入月薪范围，最大薪资不能<br />超过最小薪资的3倍。如：3-6千元 </p>
        <p class="field_note_fade">请输入3~100的数字</p>
      </div>
      <input class="kuang01" v-model.number="low" type="text">
      <p class="salary_label">— 最高</p> <br />
      <p class="salary_note_fade">请输入3~100的数字</p>
      <input class="kuang02" v-model.number="high" type="text">
      <!--   <p class="field_note_fade">支持 jpg,png,gif,bmp,psd,tiff等</p>-->
    </div>
    <div class="form_field">
      <p class="form_field_label">职位福利</p>
      <input type="text" v-model="welfare" class="form_value_input" placeholder="如：提供住宿，缴纳五险，缴纳五险一金">
    </div>
    <div class="form_field">
      <p class="form_field_label">工作经验</p>
      <!-- <input type="text" class="form_value_input" placeholder="不限">-->
      <select name="b" id="" v-model="experience" class="form_value_input">
        <option value="不限">不限</option>
        <option value="应届生">应届生</option>
        <option value="1～3">1～3</option>
        <option value="3～5">3～5</option>
        <option value="5～10">5～10</option>
        <option value="10年以上">10年以上</option>
      </select>
    </div>
    <div class="form_field">
      <div class="form_field_label01">
        <p class="title_node">学历要求</p>
        <p class="field_note_light">最低学历要求</p>
      </div>
      <!--<input type="text" class="school_value_input">-->
      <select name="c" id="" v-model="education" class="school_value_input">
        <option value="不限">不限</option>
        <option value="初中">初中</option>
        <option value="中专">中专</option>
        <option value="高中">高中</option>
        <option value="大专">大专</option>
        <option value="本科">本科</option>
        <option value="硕士">硕士</option>
        <option value="博士">博士</option>
      </select>

    </div>
    <div class="form_field">
      <p class="form_field_label">其他要求</p>
      <input type="text" v-model="requirement" class="form_value_input" placeholder="如：技能、证书、操作系统等">
    </div>
    <div class="form_field">
      <!-- <p class="form_field_label01">公司对外简称 <br />-->
      <div class="form_field_label01">
        <p class="title_node">工作地点</p>
      </div>
      <div>
        <input type="text" class="form_input" placeholder="中国">
        <input type="text" class="form_input">
        <br />
        <input type="text" class="form_value_input01" placeholder="如：智士网络（1~5个字）">
      </div>
    </div>
    <div class="form_field">
      <p class="form_field_label">面试地点</p>
      <input  type="radio" id="place01" name="place" value="同工作地点" v-model="place">
      <label for="place01">同工作地点</label>
      <input class="form_radio" type="radio" @click="isUser = !isUser" id="place02" name="place" value="其他" v-model="place">
      <label for="place02">其他</label>
    </div>

    <div class="form_field">
      <p class="form_field_label">面试安排</p>
      <div class="interview_select">
        <div class="select_item_first">
          <input type="checkbox" value="周一" v-model="week"><label>周一</label>
        </div>
        <div class="select_item_second">
          <input class="form_checkbox" type="checkbox" value="周二" v-model="week"><label>周二</label>
        </div>
        <div class="select_item">
          <input class="form_checkbox" type="checkbox" value="周三" v-model="week"><label>周三</label>
        </div>
        <div class="select_item">
          <input class="form_checkbox" type="checkbox" value="周四" v-model="week"><label>周四</label>
        </div> <br />
        <div class="select_item">
          <input class="form_checkbox" type="checkbox" value="周五" v-model="week"><label>周五</label>
        </div>
        <div class="select_item">
          <input class="form_checkbox_six" type="checkbox" value="周六" v-model="week"><label>周六</label>
        </div>
        <div class="select_item">
          <input class="form_checkbox" type="checkbox" value="周日" v-model="week"><label>周日</label>
        </div>
        <div class="select_item">
          <input class="form_checkbox" type="checkbox" value="节假日除外" v-model="week"><label>节假日除外</label>
        </div>

      </div>
    </div>

    <div class="form_field">
      <p class="form_field_label">开始面试</p>
      <input class="time01" v-model="begin" type="text">
      <p class="form_field_label">结束面试</p>
      <input class="time02" v-model="over" type="text">
    </div>
    <div class="form_field">
      <p class="form_field_label">面试联系人</p>
      <div class="insert_icon">
        <i class="input_icon name_icon"></i>
        <input type="text" v-model="linkman" class="user_value_input" placeholder="   只支持一位联系人">
      </div>
    </div>

    <div class="form_field">
      <p class="form_field_label">联系人手机</p>
      <div class="insert_icon">
        <i class="input_icon phone_icon"></i>
        <input type="text" v-model="mobile" class="mobile_value_input" placeholder="   只支持一个手机号码">
      </div>
    </div>
    <div class="form_field">
      <!-- <p class="form_field_label01">公司对外简称 <br />-->
      <div class="form_field_label01">
        <p class="title_node">面试备注</p>
        <p class="field_note_light">面试安排及特别说明事项</p>
      </div>
      <textarea  v-model="remark" class="comments" placeholder="如：周一到周五9点到12点可面试，须携带本人身份证">
     </textarea>
    </div>

  </div>
</template>

<script>
  export default {
    name: "issue",
    data() {
      return {
        place: '',
        week: '',
        enterprisecode: '',
        enterprisename: '',
        shortname: '',
        positonname: '',
        skill: '',
        kinds: '全职',
        experience: '不限',
        education: '不限',
        num: '',
        description: '',
        low: '',
        high: '',
        welfare: '',
        requirement: '',
        begin: '',
        over: '',
        linkman: '',
        remark: ''
      }
    }
  }
</script>

<style scoped>
</style>

