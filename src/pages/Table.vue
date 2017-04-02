<template>
  <div class="container">
      <h3>公益性行业专项 OPMD 患者登记表(初诊)</h3>
      <table class="table table-bordered">
        <tbody>
          <tr>
            <td rowspan="8">基本信息</td>
            <td>患者编号</td>
            <td>
              <input type="text" v-model="patient.baseinfo.number" class="form-control">
            </td>
            <td>患者姓名</td>
            <td>
              <input type="text" v-model="patient.baseinfo.name" class="form-control">
            </td>
            <td>性别</td>
            <td>
              <input type="radio" id="one" value="0" v-model="patient.baseinfo.gender">
              <label for="one">F</label>
              <input type="radio" id="two" value="1" v-model="patient.baseinfo.gender">
              <label for="two">M</label>
            </td>
          </tr>
          <tr>
            <td>身份证号</td>
            <td colspan="2">
              <input type="text" v-model="patient.baseinfo.card_num" class="form-control">
            </td>
            <td>就诊病历号</td>
            <td colspan="2">
              <input type="text" v-model="patient.baseinfo.case_num" class="form-control">
            </td>
          </tr>
          <tr>
            <td>手机</td>
            <td>
              <input type="text" v-model="patient.baseinfo.name" class="form-control">
            </td>
            <td>固话(加区号)</td>
            <td>
              <input type="text" v-model="patient.baseinfo.name" class="form-control">
            </td>
            <td>Email</td>
            <td>
              <input type="text" v-model="patient.baseinfo.name" class="form-control">
            </td>
          </tr>
          <tr>
            <td>住址</td>
            <td colspan="3">
              <input type="text" v-model="patient.baseinfo.address" class="form-control">
            </td>
            <td>QQ/weixin</td>
            <td>
              <input type="text" v-model="patient.baseinfo.qq_weixin" class="form-control">
            </td>
          </tr>
          <tr>
            <td>就业状态</td>
            <td colspan="3">
              <input type="radio" id="j_s_1" value="1" v-model="patient.baseinfo.job_status">
              <label for="j_s_1">在职</label>
              <input type="radio" id="j_s_2" value="2" v-model="patient.baseinfo.job_status">
              <label for="j_s_2">待业</label>
              <input type="radio" id="j_s_3" value="3" v-model="patient.baseinfo.job_status">
              <label for="j_s_3">退休</label>
              <input type="radio" id="j_s_0" value="0" v-model="patient.baseinfo.job_status">
              <label for="j_s_0">其它</label>
            </td>
            <td>(原)主要职业</td>
            <td>
              <input type="text" v-model="patient.baseinfo.job" class="form-control">
            </td>
          </tr>
          <tr>
            <td>教育程度</td>
            <td colspan="5">
              <input type="radio" id="e_s_1" value="1" v-model="patient.baseinfo.job_status">
              <label for="j_s_1">小学</label>
              <input type="radio" id="e_s_2" value="2" v-model="patient.baseinfo.job_status">
              <label for="j_s_2">中学</label>
              <input type="radio" id="e_s_3" value="3" v-model="patient.baseinfo.job_status">
              <label for="j_s_3">大学或以上</label>
              <input type="radio" id="e_s_0" value="0" v-model="patient.baseinfo.job_status">
              <label for="j_s_0">其它</label>
            </td>
          </tr>
          <tr>
            <td>居住地区</td>
            <td colspan="5">
              <input type="radio" id="l_a_1" value="1" v-model="patient.baseinfo.living_area">
              <label for="l_a_1">市区</label>
              <input type="radio" id="l_a_2" value="2" v-model="patient.baseinfo.living_area">
              <label for="l_a_2">郊区</label>
              <input type="radio" id="l_a_3" value="3" v-model="patient.baseinfo.living_area">
              <label for="l_a_3">农村</label>
              <input type="radio" id="l_a_0" value="0" v-model="patient.baseinfo.living_area">
              <label for="l_a_0">其它</label>
            </td>
          </tr>
          <tr>
            <td>居住状态</td>
            <td colspan="5">
              <input type="radio" id="l_s_1" value="1" v-model="patient.baseinfo.living_status">
              <label for="l_s_1">独居</label>
              <input type="radio" id="l_s_2" value="2" v-model="patient.baseinfo.living_status">
              <label for="l_s_2">与同伴合居</label>
              <input type="radio" id="l_s_3" value="3" v-model="patient.baseinfo.living_status">
              <label for="l_s_3">与家人合居</label>
              <input type="radio" id="l_s_0" value="0" v-model="patient.baseinfo.living_status">
              <label for="l_s_0">其它</label>
            </td>
          </tr>
        </tbody>

      </table>

      <table class="table table-bordered">
        <tbody>
        <tr>
          <td rowspan="13">流行病学调查</td>
          <td rowspan="4">吸烟</td>
          <td>吸烟</td>
          <td>
            <input type="checkbox" v-model="patient.epibio.smoke.smoke">
          </td>
          <td>始吸年龄</td>
          <td>(<input type="text" v-model="patient.epibio.smoke.start_age" class="form-control">)岁</td>
        </tr>
        <tr>
          <td>是否戒烟</td>
          <td>
            <input type="checkbox" v-model="patient.epibio.smoke.quit">
          </td>
          <td>平均烟量</td>
          <td>
            (<input type="text" v-model="patient.epibio.smoke.amount" class="form-control">)支/天
          </td>
        </tr>
        <tr>
          <td>吸烟类型</td>
          <td>
            <input type="radio" id="s_t_1" value="1" v-model="patient.epibio.smoke.type">
            <label for="s_t_1">过滤嘴</label>
            <input type="radio" id="s_t_2" value="2" v-model="patient.epibio.smoke.type">
            <label for="s_t_2">非过滤嘴</label>
            <input type="radio" id="s_t_3" value="3" v-model="patient.epibio.smoke.type">
            <label for="s_t_3">其它</label>
          </td>
          <td>戒烟时长</td>
          <td>
            (<input type="text" v-model="patient.epibio.smoke.quit_time" class="form-control">)月
          </td>
        </tr>
        <tr>
          <td>被动吸烟</td>
          <td>
            <input type="checkbox" v-model="patient.epibio.smoke.passive">
          </td>
          <td>备 注</td>
          <td>
            <textarea type="text" v-model="patient.epibio.smoke.note" class="form-control"></textarea>
          </td>
        </tr>
        <tr>
          <td rowspan="4">饮 酒</td>
          <td>饮 酒</td>
          <td>
            <input type="checkbox" v-model="patient.epibio.drink.drink">
          </td>
          <td>开始年龄</td>
          <td>
            (<input type="text" v-model="patient.epibio.drink.start_age" class="form-control">)岁
          </td>
        </tr>
        <tr>
          <td>是否戒酒</td>
          <td><input type="checkbox" v-model="patient.epibio.smoke.quit"></td>
          <td>平均酒量</td>
          <td>(<input type="text" v-model="patient.epibio.drink.amount" class="form-control">)ml/天</td>
        </tr>
        <tr>
          <td>主要类型</td>
          <td>
            <input type="radio" id="d_t_1" value="1" v-model="patient.epibio.drink.type">
            <label for="d_t_1">白酒</label>
            <input type="radio" id="d_t_2" value="2" v-model="patient.epibio.drink.type">
            <label for="d_t_2">红酒</label>
            <input type="radio" id="d_t_3" value="3" v-model="patient.epibio.drink.type">
            <label for="d_t_3">啤酒</label>
            <input type="radio" id="d_t_0" value="0" v-model="patient.epibio.drink.type">
            <label for="d_t_0">其它</label>
          </td>
          <td>戒酒时长</td>
          <td>
            (<input type="text" v-model="patient.epibio.drink.quit_time" class="form-control">)月
          </td>
        </tr>
        <tr>
          <td>备 注</td>
          <td colspan="3">
            <textarea type="text" v-model="patient.epibio.drink.note" class="form-control"></textarea>
          </td>
        </tr>
        <tr>
          <td>咀嚼槟榔</td>
          <td colspan="2">
            <input type="checkbox" v-model="patient.epibio.betel.chew">
            每日用量
            (<input type="text" v-model="patient.epibio.betel.dose" class="form-control">)

          </td>
          <td>咀嚼烟叶</td>
          <td colspan="2">
            <input type="checkbox" v-model="patient.epibio.tabacoo.chew">
            每日用量
            (<input type="text" v-model="patient.epibio.tabacoo.dose" class="form-control">)
          </td>
        </tr>
        <tr>
          <td>饮食</td>
          <td colspan="4">
            <input type="radio" id="f_1" value="1" v-model="patient.epibio.food_type">
            <label for="f_1">辛辣</label>
            <input type="radio" id="f_2" value="2" v-model="patient.epibio.food_type">
            <label for="f_2">清淡</label>
            <input type="radio" id="f_3" value="3" v-model="patient.epibio.food_type">
            <label for="f_3">烫食</label>
            <input type="radio" id="f_0" value="4" v-model="patient.epibio.food_type">
            <label for="f_0">其他</label>
          </td>
        </tr>
        <tr>
          <td>系统病史</td>
          <td colspan="4">
            <input type="checkbox" v-model="patient.epibio.sys_d.has">
            (注明具体疾病名称)
            <input type="text" v-model="patient.epibio.sys_d.desc" class="form-control">
          </td>
        </tr>
        <tr>
          <td>家 族 史</td>
          <td colspan="4">
            <input type="checkbox" v-model="patient.epibio.fami_d.has">
            (注明与患者关系)
            <input type="text" v-model="patient.epibio.fami_d.desc" class="form-control">
          </td>
        </tr>
        <tr>
          <td>长期服药</td>
          <td colspan="4">
            <input type="checkbox" v-model="patient.epibio.long_drug.has">
            (主要种类、剂量及持续时间)
            <input type="text" v-model="patient.epibio.long_drug.desc" class="form-control">
          </td>
        </tr>
        </tbody>
      </table>

    <table class="table table-bordered">
      <tbody>
        <tr>
          <td>诊断</td>
          <td colspan="3">
            <input type="radio" id="dia_1" value="1" v-model="patient.clinical.diagnosis">
            <label for="dia_1">1.OLK 或其癌变患者(进入“OLK 临床表现”部分)</label>
            <br>
            <input type="radio" id="dia_2" value="2" v-model="patient.clinical.diagnosis">
            <label for="dia_2">2.OLP 或其癌变患者(进入“OLP 临床表现”部分)</label>
          </td>
        </tr>
        <tr>
          <td>病程</td>
          <td>(<input type="text" v-model="patient.clinical.d_course" class="form-control">)月</td>
          <td>主观症状</td>
          <td>
            <input type="radio" id="sym_0" value="0" v-model="patient.clinical.symptom">
            <label for="sym_0">无不适</label>
            <input type="radio" id="sym_1" value="1" v-model="patient.clinical.symptom">
            <label for="sym_1">粗糙感</label>
            <input type="radio" id="sym_2" value="2" v-model="patient.clinical.symptom">
            <label for="sym_2">刺激痛</label>
            <input type="radio" id="sym_3" value="3" v-model="patient.clinical.symptom">
            <label for="sym_3">自发痛</label>
          </td>
        </tr>
      </tbody>

    </table>
    <h3>OLK临床表现</h3>
    <table class="table table-bordered">
      <thead>
      <tr>
        <th>部 位<br>(详述具体部位)</th>
        <th>填写格式:<br>最长径(mm) x 与最长径垂直的最长径(mm)</th>
        <th>分型</th>
        <th>图片</th>
        <th>癌变</th>
        <th></th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="site in patient.olk.sites">
        <td><input type="text" v-model="site.site" class="form-control"></td>
        <td>
          <input type="text" v-model="site.s_long" class="form-control"> x <input type="text" v-model="site.s_wide" class="form-control">
        </td>
        <td>
          <select v-model="site.type">
            <option v-for="type in types" :value="type.value">
              {{ type.text }}
            </option>
          </select>
        </td>
        <td>
          <!-- <input type="file" v-model="site.img"> -->
        </td>
        <td>
          <input type="checkbox" v-model="site.cancer">
        </td>
        <td>
          <button class="btn btn-danger btn-sm" @click.prevent="removeOlkSiteLine(site)"><i class="fa fa-times"></i></button>
        </td>
      </tr>
      <tr>
        <button class="btn btn-primary btn-sm" @click.prevent="addOlkSiteLine"><i class="fa fa-plus"></i></button>
      </tr>
      </tbody>
    </table>

    <h3>OLP临床表现</h3>
    <table class="table table-bordered">
      <thead>
      <tr>
        <th>部 位</th>
        <th>白纹累及 <br>
          (四分法)*</th>
        <th>充血面积 <br>
          (四分法)</th>
        <th>糜烂面积 <br>
          最长径(mm) x 与最长径垂直的最长径(mm)</th>
          <th>图片</th>
        <th>癌变</th>
        <th></th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="site in patient.olp.sites">
        <td>
          <select v-model="site.site">
            <option v-for="site in olp_sites" :value="site.value">
              {{ site.text }}
            </option>
          </select>
        </td>
        <td>
          <select v-model="site.bw">
            <option v-for="quart in quarts" :value="quart.value">
              {{ quart.text }}
            </option>
          </select>
        </td>
        <td>
          <select v-model="site.cx">
            <option v-for="quart in quarts" :value="quart.value">
              {{ quart.text }}
            </option>
          </select>
        </td>

        <td>
          <input type="text" v-model="site.ml_long" class="form-control"> X <input type="text" v-model="site.ml_wide" class="form-control">
        </td>
        <td>
          <!-- <input type="file" v-model="site.img"> -->
        </td>
        <td>
          <input type="checkbox" v-model="site.cancer">
        </td>
        <td>
          <button class="btn btn-danger btn-sm" @click.prevent="removeOlpSiteLine(site)"><i class="fa fa-times"></i></button>
        </td>
      </tr>
      <tr>
        <td colspan="3">
          <button class="btn btn-primary btn-sm" @click.prevent="addOlpSiteLine"><i class="fa fa-plus"></i></button>
        </td>
        <td colspan="2">
          <select v-model="patient.olp.olp_type">
            <option v-for="type in olp_types" :value="type.value">
              {{ type.text }}
            </option>
          </select>
        </td>
        <td colspan="2">
          <input type="text" v-mode="patient.olp.ml_area">
        </td>
      </tr>
      </tbody>
    </table>
    <h3>目测最具癌变潜能部位(除初诊时检查的部位以外,复诊时可增加其他部位)</h3>
    <table class="table table-bordered">
      <thead>
      <tr>
        <th>部位 <br>(详述具体部位)</th>
        <th>Velscope</th>
        <th>甲苯胺蓝染色</th>
        <th>组织病理结果 <br>(异常增生程度)</th>
        <th></th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="cancer in patient.result.cancers">
        <td>
          <input type="text" v-model="cancer.site" class="form-control">
        </td>
        <td>
          <select v-model="cancer.velscope">
            <option v-for="type in cancer_types" :value="type.value">
              {{ type.text }}
            </option>
          </select>
          <br>
          <!-- <input type="file" v-model="cancer.v_img"> -->
        </td>
        <td>
          <select v-model="cancer.toluidine">
            <option v-for="type in cancer_types" :value="type.value">
              {{ type.text }}
            </option>
          </select>
          <br>
          <!-- <input type="file" v-model="cancer.t_img"> -->
        </td>
        <td>
          <select v-model="cancer.velscope">
            <option v-for="type in cancer_status" :value="type.value">
              {{ type.text }}
            </option>
          </select>
          <br>
          <!-- <input type="file" v-model="cancer.b_img"> -->
        </td>
        <td>
          <button class="btn btn-danger btn-sm" @click.prevent="removeCancerSiteLine(cancer)"><i class="fa fa-times"></i></button>
        </td>
      </tr>
      <tr>
        <td colspan="2">
          <button class="btn btn-primary btn-sm" @click.prevent="addCancerSiteLine"><i class="fa fa-plus"></i></button>
        </td>
      </tr>
      </tbody>
    </table>
    <table class="table table-bordered">
      <tbody>
      <tr>
        <td rowspan="4">检查</td>
        <td rowspan="3">口腔局部刺激因素</td>
        <td>尖锐牙尖</td>
        <td colspan="5">
          <input type="checkbox" v-model="patient.result.sharp_teeth">
        </td>
      </tr>
      <tr>
        <td>不良修复体</td>
        <td colspan="5">
          <input type="checkbox" v-model="patient.result.bad_fit">
        </td>
      </tr>
      <tr>
        <td>牙结石</td>
        <td colspan="5">
          <select v-model="patient.result.calculus">
            <option v-for="type in calculus_types" :value="type.value">
              {{ type.text }}
            </option>
          </select>
        </td>
      </tr>
      <tr>
        <td>全身检查报告</td>
        <td>血常规</td>
        <td>
        <input type="checkbox" v-model="patient.result.blood.has">
        <!-- <input type="file" v-model="patient.result.blood.img"> -->
        </td>
        <td>血糖</td>
        <td>
           <input type="checkbox" v-model="patient.result.blood_sugar.has">
        <!-- <input type="file" v-model="patient.result.blood_sugar.img"> -->
        </td>
        <td>肝肾功</td>
        <td>
           <input type="checkbox" v-model="patient.result.liver.has">
        <!-- <input type="file" v-model="patient.result.liver.img"> -->
        </td>
      </tr>
      <tr>
        <td rowspan="2" colspan="2">处理措施</td>
        <td>全身用药</td>
        <td colspan="5">
          <input type="checkbox" v-model="patient.result.sys_drug.has">
          (药名及疗程)
          <br>
          <div class="input-group">
            <div class="row" v-for="treat in patient.result.sys_drug.treats">
              <div class="col-sm-5">
                <input type="text" v-model="treat.drug">
              </div>
              <div class="col-sm-5">
                <input type="text" v-model="treat.time">
              </div>
              <div class="col-sm-2">
                <button class="btn btn-danger btn-sm" @click.prevent="removeSysTreatLine(treat)">
                  X
                </button>
              </div>
            </div>
            <div class="row">
              <button class="btn btn-primary btn-sm" @click.prevent="addSysTreatLine"><i class="fa fa-plus"></i></button>
            </div>
          </div>
        </td>
      </tr>
      <tr>
        <td>局部用药</td>
        <td colspan="5">
          <input type="checkbox" v-model="patient.result.topical_drug.has">
          (药名及疗程)
          <br>
          <div class="input-group">
            <div class="row" v-for="treat in patient.result.topical_drug.treats">
              <div class="col-sm-5">
                <input type="text" v-model="treat.drug">
              </div>
              <div class="col-sm-5">
                <input type="text" v-model="treat.time">
              </div>
              <div class="col-sm-2">
                <button class="btn btn-danger btn-sm" @click.prevent="removeTopicalTreatLine(treat)">
                  X
                </button>
              </div>
            </div>
            <div class="row">
              <button class="btn btn-primary btn-sm" @click.prevent="addTopicalTreatLine"><i class="fa fa-plus"></i></button>
            </div>
          </div>
        </td>
      </tr>
      <tr>
        <td colspan="2">备注(上述表格未包含的其他内容)</td>
        <td colspan="6">
          <textarea class="form-control" v-model="patient.result.note"></textarea>
        </td>
      </tr>
      </tbody>
    </table>
    <h3></h3>
  </div>
</template>
<script>
  export default {
    data () {
      return {
        patient: {
          baseinfo: {
            number: '',
            name: '',
            gender: 0,
            card_num: '',
            case_num: '',
            mobile: '',
            phone: '',
            email: '',
            address: '',
            qq_weixin: '',
            job_status: 0,
            job: '',
            education: 0,
            living_area: 0,
            living_status: 0
          },
          epibio: {
            smoke: {
              smoke: 0,
              start_age: 0,
              quit: 0,
              amount: 0,
              type: 0,
              quit_time: 0,
              passive: 0,
              note: ''
            },
            drink: {
              drink: 0,
              start_age: 0,
              quit: 0,
              amount: 0,
              type: 0,
              quit_time: 0,
              note: ''
            },
            betel: {
              chew: 0,
              dose: 0
            },
            tabacoo: {
              chew: 0,
              dose: 0
            },
            food_type: 0,
            sys_d: {
              has: 0,
              desc: ''
            },
            fami_d: {
              has: 0,
              desc: ''
            },
            long_drug: {
              has: 0,
              desc: ''
            }
          },
          clinical: {
            diagnosis: 0,
            d_course: 0,
            symptom: 0
          },
          olp: {
            ml_area: 0,
            olp_type: 0,
            sites: [
              {
                site: 0,
                bw: 0,
                cx: 0,
                ml_long: 0,
                ml_wide: 0,
                img: '',
                cancer: 0
              }
            ]
          },
          olk: {
            sites: [
              {
                site: 0,
                s_long: 0,
                s_wide: 0,
                type: 0,
                img: '',
                cancer: 0
              }
            ]
          },
          result: {
            cancers: [
              {
                site: 0,
                velscope: 0,
                v_img: '',
                toluidine: 0,
                t_img: '',
                biospy: 0,
                b_img: ''
              }
            ],
            blood: {
              has: 0,
              img: ''
            },
            blood_sugar: {
              has: 0,
              img: ''
            },
            liver: {
              has: 0,
              img: ''
            },
            sharp_teeth: 0,
            bad_fit: 0,
            calculus: 0,
            sys_drug: {
              has: 0,
              treats: [
                {
                  drug: '',
                  time: 0
                }
              ]
            },
            topical_drug: {
              has: 0,
              treats: [
                {
                  drug: '',
                  time: 0
                }
              ]
            },
            note: ''
          }
        },
        types: [
          { text: '斑块状', value: 'A' },
          { text: '皱纸状', value: 'B' },
          { text: '颗粒状', value: 'C' },
          { text: '疣状', value: 'D' },
          { text: '溃疡状', value: 'E' }
        ],
        quarts: [
          { text: '未见病损', value: '0' },
          { text: '1/4', value: '1' },
          { text: '2/4', value: '2' },
          { text: '3/4', value: '3' },
          { text: '4/4', value: '4' }
        ],
        olp_sites: [
          { text: '双唇', value: '1' },
          { text: '右颊', value: '2' },
          { text: '左颊', value: '3' },
          { text: '舌背', value: '4' },
          { text: '舌腹', value: '5' },
          { text: '口底', value: '6' },
          { text: '硬腭', value: '7' },
          { text: '软腭', value: '8' },
          { text: '上颌牙龈', value: '9' },
          { text: '下颌牙龈', value: '10' }
        ],
        olp_types: [
          { text: '斑纹型', value: '1' },
          { text: '充血型', value: '2' },
          { text: '糜烂型', value: '3' }
        ],
        cancer_types: [
          { text: '+', value: '1' },
          { text: '-', value: '2' },
          { text: '±', value: '3' }
        ],
        cancer_status: [
          { text: '无', value: '0' },
          { text: '轻', value: '2' },
          { text: '中', value: '3' },
          { text: '重', value: '4' },
          { text: '癌', value: '5' },
          { text: '其他', value: '6' }
        ],
        calculus_types: [
          { text: '无', value: '0' },
          { text: 'I°', value: '1' },
          { text: 'II°', value: '2' },
          { text: 'III°', value: '3' }
        ]
      }
    },
    methods: {
      removeOlkSiteLine (site) {
      },
      addOlkSiteLine () {
      },
      removeOlpSiteLine (site) {
      },
      addOlpSiteLine () {
      },
      removeCancerSiteLine (site) {
      },
      addCancerSiteLine () {
      },
      addSysTreatLine () {
      },
      removeSysTreatLine (treat) {
      },
      addTopicalTreatLine () {
      },
      removeTopicalTreatLine (treat) {
      }
    }
  }
</script>
