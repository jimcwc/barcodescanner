# barcodescanner

本工程将扫描的功能抽取出来当做一个module来使用，别的项目使用时直接将本项目下载下来，当做module 导入即可。


主要的调用方法



<pre><code> 
     Intent intent = new Intent(this,CaptureActivity.class);
     startActivityForResult(intent,GETSCAN);


//////捕捉返回的扫描结果
    @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        if(resultCode == 12000){
            switch (requestCode){
                case GETSCAN:{
                 String numb=  data.getStringExtra("Result");
                    showTv.setText(numb);
                    break;
                }
            }
        }
    }
</code></pre>
