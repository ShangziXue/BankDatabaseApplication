<template>
    <div>
        <form onSubmit="return false" class="form">
            <h1>注册界面</h1>
            <table align="center" class="emptytable" >
                <tr>
                    <td>&emsp;&emsp;&emsp;&emsp;<font color="red">*</font> 账户类型</td>
                    <td>
                        <div class="radio">
                        <input id="radio-1" type="radio" name="type" v-model="type" value="SUB_BANK" required="true" />
                        <label for="radio-1" class="radio-label">支行账户</label>&emsp;
                        <input id="radio-2" type="radio" name="type" v-model="type" value="CUSTOMER" required="true" />
                        <label for="radio-2" class="radio-label">客户账户</label>&emsp;
                        <input id="radio-3" type="radio" name="type" v-model="type" value="EMPLOYEE" required="true" />
                        <label for="radio-3" class="radio-label">员工账户</label>&emsp;&emsp;&emsp;&ensp;
                        </div>
                    </td>
                </tr>
                <tr>
                    <td v-if="type === 'SUB_BANK'"><font color="red">*</font> 支行名称</td>
                    <td v-else><font color="red">*</font> 身份证号</td>
                    <td>
                        <input
                            class="input"
                            v-if="type === 'SUB_BANK'"
                            type="text"
                            placeholder="Please enter the name of bank"
                            id="username"
                            v-model="username"
                            required="true"
                            style=" width:445px;font-family: 'Fira Code', '汉仪南宫体简';"
                        />
                        <input
                            v-else
                            type="text"
                            class="input"
                            placeholder="Please enter the ID"
                            id="username"
                            v-model="username"
                            required="true"
                            style=" width:445px;font-family: 'Fira Code', '汉仪南宫体简';"
                        />
                    </td>
                </tr>
                <tr v-if="type === 'SUB_BANK'">
                    <td>所在城市</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the city of bank"
                            id="city"
                            v-model="city"
                            required="false"
                            style=" width:445px;font-family: 'Fira Code', '汉仪南宫体简';"
                        />
                    </td>
                </tr>
                <tr v-if="type === 'SUB_BANK'">
                    <td>资产总额</td>
                    <td>
                        <input
                            type="number"
                            class="input"
                            placeholder="Please enter the total money of bank"
                            id="money"
                            v-model="money"
                            required="false"
                            style=" width:445px;font-family: 'Fira Code', '汉仪南宫体简';"
                        />
                    </td>
                </tr>
                <tr v-if="type === 'CUSTOMER'">
                    <td>姓名</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the name of customer"
                            id="name"
                            v-model="name"
                            required="false"
                            style=" width:445px;font-family: 'Fira Code', '汉仪南宫体简';"
                        />
                    </td>
                </tr>
                <tr v-if="type === 'CUSTOMER'">
                    <td>联系电话</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the telphone number of customer"
                            id="tel"
                            v-model="tel"
                            required="false"
                            style=" width:445px;font-family: 'Fira Code', '汉仪南宫体简';"
                        />
                    </td>
                </tr>
                <tr v-if="type === 'CUSTOMER'">
                    <td>家庭住址</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the address of customer"
                            id="addr"
                            v-model="addr"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'CUSTOMER'">
                    <td>联系人姓名</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the name of contact"
                            id="name_link"
                            v-model="name_link"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'CUSTOMER'">
                    <td>联系人手机号</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the telphone of contact"
                            id="tel_link"
                            v-model="tel_link"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'CUSTOMER'">
                    <td>联系人Email</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the E-mail of contact"
                            id="email_link"
                            v-model="email_link"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'CUSTOMER'">
                    <td>联系人与客户关系</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the relationship of contact and customer"
                            id="relation"
                            v-model="relation"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'EMPLOYEE'">
                    <td>姓名</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the name of staff"
                            id="name"
                            v-model="name"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'EMPLOYEE'">
                    <td>所在部门</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the department ID of staff"
                            id="dept"
                            v-model="dept"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'EMPLOYEE'">
                    <td>所在支行</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the bank name of staff"
                            id="dept"
                            v-model="bankname"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'EMPLOYEE'">
                    <td>电话号码</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the telphone number of staff"
                            id="tel"
                            v-model="tel"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'EMPLOYEE'">
                    <td>家庭住址</td>
                    <td>
                        <input
                            type="text"
                            class="input"
                            placeholder="Please enter the address of staff"
                            id="addr"
                            v-model="addr"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr v-if="type === 'EMPLOYEE'">
                    <td>入职时间</td>
                    <td>
                        <input
                            type="date"
                            class="input"
                            placeholder="Please enter the entry date of staff"
                            id="date"
                            v-model="date"
                            required="false"
                            style=" width:445px;
                        font-family: 'Fira Code', '汉仪南宫体简';
                        "
                        />
                    </td>
                </tr>
                <tr>
                    <td><font color="red">*</font> 密码</td>
                    <td>
                        <input
                            type="password"
                            class="input"
                            placeholder="Please enter your password"
                            id="password"
                            v-model="password"
                            required="true"
                            style=" width:445px;
                    font-family: 'Fira Code', '汉仪南宫体简';
                    "
                        />
                    </td>
                </tr>
                <tr>
                    <td><font color="red">*</font> 重复密码</td>
                    <td>
                        <input
                            type="password"
                            class="input"
                            placeholder="Please enter your password again"
                            id="password2"
                            v-model="password2"
                            required="true"
                            style=" width:445px;
                    font-family: 'Fira Code', '汉仪南宫体简';
                    "
                        />
                    </td>
                </tr>
            </table>

            <label style="font-family:汉仪南宫体简;color:red;font-size:15px;">注：带*的字段必须填写，密码必须由6位字母或数字组成。</label><br />
        </form>
        <br />
        <button class="buttonred" v-on:click="submit()"><span>提交</span></button>
    </div>
</template>

<script>
import XEUtils from "xe-utils";
import XEAjax from "xe-ajax";
export default {
    name: "login",
    data: function() {
        return {
            type: "",
            username: "",
            password: "",
            password2: "",
            name: "",
            city: "",
            money: "",
            tel: "",
            addr: "",
            name_link: "",
            tel_link: "",
            email_link: "",
            relation: "",
            dept: "",
            date: "",
            bankname: ""
        };
    },
    created() {
        this.type = "SUB_BANK";
    },
    methods: {
        submit: function() {
            if (this.type == "" || this.username == "" || this.password == "") {
                window.alert("必填字段不能为空");
                return;
            }
            if (this.password.length != 6) {
                window.alert("密码长度必须为6位");
                return;
            }
            for (var i = 0; i < this.password.length; i++) {
                var x = this.password.charAt(i);
                if (!((x >= "0" && x <= "9") || (x >= "a" && x <= "z") || (x >= "A" && x <= "Z"))) {
                    window.alert("密码非法");
                    return;
                }
            }
            if (this.password !== this.password2) {
                window.alert("两次输入的密码不相同");
            } else {
                this.$http
                    .post(
                        "http://" + document.domain + ":5000/register",
                        {
                            type: this.type,
                            username: this.username,
                            password: this.password,
                            name: this.name,
                            city: this.city,
                            money: this.money,
                            tel: this.tel,
                            addr: this.addr,
                            name_link: this.name_link,
                            tel_link: this.tel_link,
                            email_link: this.email_link,
                            relation: this.relation,
                            dept: this.dept,
                            bankname: this.bankname,
                            date_s: XEUtils.toDateString(this.date, "yyyy-MM-dd")
                        },
                        {
                            emulateJSON: true
                        }
                    )
                    .then(function(response) {
                        //console.log(response.status);
                        if (parseInt(response.body.code) === 200) {
                            //console.log("OK");
                            localStorage.setItem("type", this.type);
                            localStorage.setItem("username", this.username);
                            this.$router.push("/index");
                            window.alert("注册成功");
                            //return;
                        } else if (parseInt(response.body.code) === 400) {
                            window.alert("用户名已存在");
                        } else {
                            window.alert("注册失败");
                        }
                    });
            }
        }
    }
};
</script>

<style>
.emptytable {
    align: right;
    border: 1px;
}
.emptytable tr {
    text-align: right;
}
.emptytable td {
    text-align: right;
}
.buttonred {
    display: inline-block;
    border-radius: 4px;
    background-color: #f4511e;
    border: none;
    color: #ffffff;
    text-align: center;
    font-size: 12px;
    padding: 20px;
    width: 100px;
    transition: all 0.5s;
    cursor: pointer;
    margin: 5px;
}
.buttonred span {
    cursor: pointer;
    display: inline-block;
    position: relative;
    transition: 0.5s;
}
.buttonred span:after {
    content: "»";
    position: absolute;
    opacity: 0;
    top: 0;
    right: -20px;
    transition: 0.5s;
}
.buttonred:hover span {
    padding-right: 25px;
}
.buttonred:hover span:after {
    opacity: 1;
    right: 0;
}
.form{
        background: #e0de83;
        width: 960px;
        height: 660px;
        margin: 35px auto;
        padding: 30px;
        box-shadow:0px 2px 4px 2px #aaaaaa,
                   inset 0px 2px 2px rgba(255,255,255,0.7);
        border-radius: 5px;
    }
.input{
    outline-style: none ;
    border: 5px solid #e0de83;
    border-radius: 6px;
    padding: 8px 14px;
    width: 720px;
    font-size: 14px;
    font-weight: 700;
    font-family: "Fira Code", "汉仪南宫体简";
}
.input:focus{
    border-color: #66afe9;
    outline: 0;
    -webkit-box-shadow: inset 0 3px 3px rgba(0,0,0,.075),0 0 8px rgba(102,175,233,.6);
    box-shadow: inset 0 3px 3px rgba(0,0,0,.075),0 0 8px rgba(102,175,233,.6)
}
td{
    font-size: 20px;
    font-weight: 700;
    font-family: "Fira Code", "汉仪南宫体简";
}
.radio {
    margin: 0.5rem;
}
.radio input[type="radio"] {
    position: absolute;
    opacity: 0;
}
.radio input[type="radio"] + .radio-label:before {
    content: '';
    background: #f4f4f4;
    border-radius: 100%;
    border: 1px solid #b4b4b4;
    display: inline-block;
    width: 1.2em;
    height: 1.2em;
    position: relative;
    top: -0.2em;
    margin-right: 0.3em;
    vertical-align: top;
    cursor: pointer;
    text-align: center;
    -webkit-transition: all 250ms ease;
    transition: all 250ms ease;
}
.radio input[type="radio"]:checked + .radio-label:before {
    background-color: #3197EE;
    box-shadow: inset 0 0 0 4px #f4f4f4;
}
.radio input[type="radio"]:focus + .radio-label:before {
    outline: none;
    border-color: #3197EE;
}
.radio input[type="radio"]:disabled + .radio-label:before {
    box-shadow: inset 0 0 0 4px #f4f4f4;
    border-color: #b4b4b4;
    background: #b4b4b4;
}
.radio input[type="radio"] + .radio-label:empty:before {
    margin-right: 0;
}
</style>
