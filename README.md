# 小组成员  
郭立、张慧斌、赵晨宇、周轩竹


# 前端框架使用说明
[帮助索引](https://www.jianshu.com/p/e2d4957993dd)
由于fork后没有issue, 不再fork开发, 请大家勤`git pull`


## 配置 yarn
可以通过以下代码检验是否安装了yarn
`yarn -v` or `yarn --version`

如果没有安装yarn可以尝试用npm代替, 如果不行可根据以下步骤安装yarn

#### macOS
可以通过Homebrew安装
```
brew install yarn
```


#### windows
可以通过[安装程序](https://yarnpkg.com/latest.msi)安装

#### [Ubuntu](https://yarnpkg.com/zh-Hans/docs/install#debian-stable)
```
sudo apt remove cmdtest
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn
```

## 安装

`yarn install --registry=https://registry.npm.taobao.org`

## 运行
`yarn run serve`


## 使用的UI

已配置Ant Design Vue, 可以参考的[文档](https://vue.ant.design/docs/vue/introduce-cn/)


## axios
实例
#### get
```js
// Make a request for a user with a given ID
axios.get('/user?ID=12345')
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });

// Optionally the request above could also be done as
axios.get('/user', {
    params: {
      ID: 12345
    }
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```
#### post
```
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```
#### 同时发送多请求
```
function getUserAccount() {
  return axios.get('/user/12345');
}

function getUserPermissions() {
  return axios.get('/user/12345/permissions');
}

axios.all([getUserAccount(), getUserPermissions()])
  .then(axios.spread(function (acct, perms) {
    // Both requests are now complete
  }));
```
