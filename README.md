> ### File --> Preferences --> Configure User Snippets --> New Global Snippets File..
>
> Then remove all content and paste this

```shell
{
	"Class with constructor": {
		"scope": "",
		"prefix": [
			"cc"
		],
		"body": [
			"class ${1:ClassName} {",
			"\tconstructor(${2:params}) {",
			"\t\t$0",
			"\t}",
			"};"
		],
		"description": "Create class with constructror function"
	},
	"Class with constructor and definition": {
		"scope": "",
		"prefix": [
			"ccd"
		],
		"body": [
			"class ${1:ClassName} {",
			"\tconstructor(${2:params}) {",
			"\t\t$0",
			"\t}",
			"};",
			"const ${4:data} = new ${1:ClassName}(${3:args});"
		],
		"description": "Create class with constructror function then define it"
	},
	"Arrow function": {
		"scope": "",
		"prefix": [
			"arfn",
		],
		"body": [
			"const ${1:name} = ($2) => {",
			"\t$0",
			"};"
		],
		"description": "Create arrow function"
	},
	"Async Arrow function": {
		"scope": "",
		"prefix": [
			"aarfn",
		],
		"body": [
			"const ${1:name} = async ($2) => {",
			"\t$0",
			"};"
		],
		"description": "Create async arrow function"
	},
	"Async function": {
		"scope": "",
		"prefix": [
			"afn"
		],
		"body": [
			"async function ${1:name}(${2:params}) {",
			"\t$0",
			"};"
		],
		"description": "Create async function"
	},
	"Log function": {
		"scope": "",
		"prefix": [
			"fnlog"
		],
		"body": [
			"function ${1:name} (${2:params}) {",
			"\treturn $0",
			"};",
			"",
			"console.log(${1:name}($3));"
		],
		"description": "Console.log function's response"
	},
	"Log arrow function": {
		"scope": "",
		"prefix": [
			"arfnlog"
		],
		"body": [
			"const ${1:name} = (${2:params}) => {",
			"\treturn $0",
			"};",
			"",
			"console.log(${1:name}($3));"
		],
		"description": "Console.log arrow function's response"
	},
	"new Promise with handling": {
		"scope": "",
		"prefix": "promhandle",
		"body": [
			"const ${1:promise} = new Promise((res, rej) => {",
			"\t$0",
			"});",
			"",
			"${1:promise}",
			"\t.then(res => { $2 })",
			"\t.catch(err => { console.log(err); });",
		],
		"description": "Create promise object anb handle"
	},
	"Return Promise with function": {
		"scope": "",
		"prefix": "returnprom",
		"body": [
			"const ${1:promise} = (${2:params}) => {",
			"\treturn new Promise((res, rej) => {",
			"\t\t$0",
			"\t});",
			"}",
			"",
			"${1:promise}(${3:args})",
			"\t.then(res => { $4 })",
			"\t.catch(err => { console.log(err); });",
		],
		"description": "Create a function which returns a promise then handle"
	},
	"Timeout Function": {
		"scope": "",
		"prefix": "timeoutfn",
		"body": [
			"const ${1:timeout} = setTimeout(function () {",
			"\t$0",
			"",
			"\tclearTimeout(this);",
			"}, 1000 * ${2:seconds})"
		],
		"description": "Create setTimeout function easily"
	},
	"Interval Function": {
		"scope": "",
		"prefix": "intervalfn",
		"body": [
			"const ${1:interval} = setInterval(function () {",
			"\t$0",
			"",
			"\tif (false) {",
			"\t\tclearInterval(this);",
			"\t}",
			"}, 1000 * ${2:seconds})"
		],
		"description": "Create setInterval function easily"
	},
	"Object Type": {
		"scope": "typescript, typescriptreact",
		"prefix": [
			"object-type",
			"objt",
			"obt"
		],
		"body": "export type ObjectType<K extends keyof any = string, V = any, A = false> = A extends true ? {[k in K]?: V} : {[k in K]: V};",
		"description": "Custom Object type"
	}
}
```