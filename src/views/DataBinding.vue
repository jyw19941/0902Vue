<template>
    <input type="text" v-model="nn" /><br>
    <input type="number" v-model.number="numberModel" />
    <div v-html="htmlString"></div>
    <div>{{ htmlString }}</div>
    <h1>Hello , {{ title }}</h1>
    <p> {{count}}회</p>
    <button @click="countUp">카운터</button>
</template>
<script>
export default{
    data(){
        return{
            title:'뷰 세상에 오신 것을 환영합니다!',
            count:0,
            htmlString: '<h2>HTML 문자열을 렌더링합니다.</h2>',
            numberModel: 3,
            nn: '안녕하세요'
        }
   },
            methods: {
            countUp: function () {
                this.count++;
        }
    }
}
</script>
<style>
@charset "UTF-8";
html {
	width: 80%;
	margin-right: auto;
	margin-left: auto;
	font-family: sans-serif;
	font-size: 16px;
	line-height: 1.5;
}

input,button,select,optgroup,textarea {
	font-family: inherit;
	font-size: inherit;
	line-height: inherit;
}

button {
	cursor: pointer;
	padding: 6px 12px;
	border-radius: 6px;
	color: #fff;
	border: 2px;
	background-color: #007bff;
	transition: background-color .2s
}
button:hover {
	background-color: #0069d9;
}
button:active {
	background-color: #003c7c;
}
button:disabled {
	opacity: .5;
	pointer-events: none;
}

input {
	padding: 6px 12px;
	border-radius: 6px;
	color: #495057;
	border: 2px solid #ced4da;
}

textarea {
	width: 500px;
	height: 200px;
}
select {
	border: 2px solid #ced4da;
}

</style>