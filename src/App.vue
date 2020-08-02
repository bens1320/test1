<template>

    <form @submit.prevent="onSubmit2">
        <label>
            <span>用户名111222:</span>
            <input type="text" v-model="user.username">
        </label>
        <br>
        <label>
            <span>密码111222:</span>
            <input type="password" v-model="user.password">
        </label>
        <button>提交</button>
    </form>
</template>

<script>
    export default {
        name: 'App',
        beforeCreate() {
            this.form = this.$form.createForm(this, {name: 'normal_login'});
        },
        data() {
            return {
                user: {
                    username: "",
                    password: ""
                }
            }
        },
        methods: {
            onSubmit() {
                // e.preventDefault();
                // @submit.prevent="onSubmit" 等价于.prevent
                this.form.validateFields((err, values) => {
                    if (!err) {
                        console.log('data: ', values);
                    } else {
                        console.log("err: ", err);
                    }
                });
            },
            onSubmit2(){
                console.log(this.user)
            }
        }
    }
</script>
<style scoped>
    #components-form-demo-normal-login .login-form {
        max-width: 300px;
    }
    #components-form-demo-normal-login .login-form-forgot {
        float: right;
    }
    #components-form-demo-normal-login .login-form-button {
        width: 100%;
    }
</style>