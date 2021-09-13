Kỹ thuật `binding` bằng cách tạo 1 `array` và duyệt nó


```` ts
public static dlgProperties = {
    titleResKey: 'dlg_name_bookmark_properties',
  };
  data: any;
  returnData: any = null;
  styles: any[] = [
    {value: 0, display: `${this.allUIResource.txtPlain}`},
    {value: 1, display: `${this.allUIResource.txtItalic}`},
    {value: 2, display: `${this.allUIResource.txtBold}`},
    {value: 3, display: `${this.allUIResource.txtBoldAndItalic}`}
  ];
  magnifications: any [] = [
    {value: 0, display: 'Fit Height'},
    {value: 1, display: 'Fit in Window'},
    {value: 2, display: 'Fit View'},
    {value: 3, display: 'Fit Visible'},
    {value: 4, display: 'Fit Width'},
    {value: 5, display: 'Fixed'},
    {value: 6, display: 'Inherit Zoom'}
  ];
  options: any[] = [
    {value: 0, display: 'Window set by user preference'},
    {value: 1, display: 'New Window'},
    {value: 2, display: 'Existing Window'}
  ];
  disabled = {'style': false, 'color': false, 'magnification': false, 'option': false};
````