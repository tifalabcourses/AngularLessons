# MultiModuleProj

ng generate module child-modules/admin --route admin --module app.module

ng generate module child-modules/sales --route sales --module app.module



ng g c  views/about-us/about-us  --module app.module
ng g c  views/invoice/invoice  --module child-modules/sales.module

ng g c  views/members/members  --module child-modules/admin.module


 {
    path: 'invoice',
    loadChildren: () => import('./child-modules/sales.module').then(m => m.SalesModule)
  }
,

 {
    path: 'members',
    loadChildren: () => import('./child-modules/admin.module').then(m => m.AdminModule)
  }
