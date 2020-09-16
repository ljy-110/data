全局loading

```js
//js文件，然后引用（网上的）
import { Loading } from 'element-ui'
// import {showLoading, hideLoading} from '@/common/loading.js'

let loading = null
const showLoading = (params) => {
    if(loading) {
        loading.close()
    }
    let options = {
        fullscreen: false,
        // target: document.querySelector('#mainLoad'),
        lock: true,
        text: '数据加载中',
        spinner: 'el-icon-loading',
        background: 'rgba(0, 0, 0, 0.7)'
    }
    Object.assign(
        options,
        params
    )
    loading = Loading.service(options)
}
const hideLoading = () => {
    loading.close()
}
export {
    showLoading,
    hideLoading
}
```

```js
//全局加载（官网）
const loading = this.$loading({
        lock: true,
        text: '获取中...',
        spinner: 'el-icon-loading',
        background: 'rgba(0, 0, 0, 0.7)'
      });
      
      loading.close();
```

