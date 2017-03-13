#[vue-router](https://router.vuejs.org/)
Vue-router is used for url direction.
Simple usage
```javascript
import VueRouter from 'vue-router'

Vue.use(VueRouter)

//requiresAuth is merely a variable
const routes = [
  { path: '/', component: Login, meta: { requiresAuth: false } },
  { path: '/login', component: Login, meta: { requiresAuth: false } },
  { path: '/main',
    component: Main,
    children: [
      { path: '', component: Realtime, meta: { requiresAuth: true } },
      { path: 'realtime', component: Realtime, meta: { requiresAuth: true } },
      { path: 'realtime/:sceneid', component: Realtime, meta: { requiresAuth: true } },
      { path: 'history', component: History, meta: { requiresAuth: true } },
      { path: 'historyChart', component: HistoryChart, meta: { requiresAuth: true } },
      { path: 'history/:sceneid', component: History, meta: { requiresAuth: true } },
      { path: 'userCenter', component: UserCenter, meta: { requiresAuth: true } },
      { path: 'systemCenter',
        component: SystemCenter,
        children: [
          { path: '', component: SystemMainConfig, meta: { requiresAuth: true } },
          { path: 'systemMainConfig', component: SystemMainConfig, meta: { requiresAuth: true } },
          { path: 'systemIconConfig', component: SystemIconConfig, meta: { requiresAuth: true } }
        ]
      },
      { path: 'deviceCenter',
        component: DeviceCenter,
        children: [
          { path: '', component: DeviceSceneConfig, meta: { requiresAuth: true } },
          { path: 'deviceSceneConfig', component: DeviceSceneConfig, meta: { requiresAuth: true } },
          { path: 'deviceChannelConfig', component: DeviceChannelConfig, meta: { requiresAuth: true } }
        ]
      },
      { path: 'DeviceCenter_2', component: DeviceCenter_2, meta: {requireAuth: true}
      },
      { path: 'Center', component: Center, meta: {requireAuth: true}
      }
    ]
  }
]

const router = new VueRouter({
  routes
})
```
Some methods before getting into these urls:
```javascript
router.beforeEach((to, from, next) => {
  console.log(to.meta.requiresAuth, AuthService.isLogin())
  if (to.meta.requiresAuth && !AuthService.isLogin()) {
    // next({
    //   path: '/login',
    //   query: { redirect: to.fullPath }
    // })
    next('/login')
  } else {
    next()
  }
})
``` 