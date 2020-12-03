---
title: 随手记
date: 2020-10-09 10:10:34
categories:
  - 笔记
---



delphi vb vfp vc++ scheme qt 易语言


```ts
patchFormValue() {
	const { currenProject, selectedComIds , unselectedComIds} = this, componentDetail = [];
	const shim = [];
	/* if (selectedComIds.length !== (currenProject._componentDetail.length)) {
		shim = this.coms.controls.slice(currenProject._componentDetail.length,
		this.coms.controls.length - currenProject._depencyDetail.length).map(v => {
		return v.value;
		})
	} */
	let _componentDetail: Array<any> = deepCopy([...currenProject._componentDetail, ...shim,
		...currenProject._depencyDetail]);
	_componentDetail = _componentDetail.filter(c => {
		return selectedComIds.includes(c.id) || unselectedComIds.includes(c.id)
	})
	this.coms.controls.forEach((v, i) => {
		_componentDetail.forEach(c => {
		if (v.value.id === c.id) {componentDetail.push(c)}
		})
		if (componentDetail.length <= i) {
		componentDetail.push(v.value)
		}
	})
	this.coms.patchValue(componentDetail, { emitEvent: true });
}

if (v.value.id === c.id) {
	v.value.propertiesList.forEach(x => {
	const flag = c.propertiesList.some(y => {
		return x.name === y.name
		// c.propertiesList.push()
	})
	if (!flag) { c.propertiesList.push(x) }
	})
}
```

Egret-Angular-Material-admin-2出现 Node Sass does not yet support your current environment: Windows 64-bit with Unsupported runtime (83) 报错，重新安装npm install --save node-sass就可以了




