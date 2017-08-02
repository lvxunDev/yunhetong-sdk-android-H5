# yunhetong-sdk-android-H5
云合同平台提供的SDK服务升级为Html5

第三方开发者只需要调用Html5页面即可


## 云合同Html5的路径 ##

    String url = "http://sdk.yunhetong.com/sdk/contract/hView?contractId=获取的合同ID&token=获取的token&noticeParams=备注字段"


| Params        | enble         |  meaning |
| ------------- |:-------------:| --------:|
| token         | Y             | 登录凭证  |
| contractId    | Y             | 合同ID   |
| noticeParams  | N             | 备注字段 |



WebView的设置

        WebView mYhtWebView = new WebView(this);
        mYhtWebView.setScrollContainer(false);
        mYhtWebView.setScrollbarFadingEnabled(false);
        mYhtWebView.setScrollBarStyle(View.SCROLLBARS_OUTSIDE_OVERLAY);
        WebSettings settings = mYhtWebView.getSettings();
        settings.setDefaultTextEncodingName("UTF-8");
        settings.setJavaScriptEnabled(true);
        settings.setSupportZoom(true);
        settings.setBuiltInZoomControls(true);
        settings.setDisplayZoomControls(false);
        settings.setLayoutAlgorithm(WebSettings.LayoutAlgorithm.NORMAL);
        settings.setUseWideViewPort(true);
        settings.setLoadWithOverviewMode(true);
        settings.setLoadsImagesAutomatically(true);
        mYhtWebView.setWebViewClient(new WebViewClient(){
            @RequiresApi(api = Build.VERSION_CODES.LOLLIPOP)
            @Override
            public boolean shouldOverrideUrlLoading(WebView view, WebResourceRequest request) {
                view.loadUrl(String.valueOf(request.getUrl()));
                return true;
            }

            @Override
            public boolean shouldOverrideUrlLoading(WebView view, String url) {
                view.loadUrl(url);
                return true;
            }
        });
       //调用云合同Html5
       mWebView.loadUrl(url);

配置可酌情删减。
