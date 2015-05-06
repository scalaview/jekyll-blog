---
layout: post
title: "Android AsyncTask and Handler"
author: scalaview
---


# AsyncTask #
你可以直接查看[AsyncTask 官方文档](http://developer.android.com/reference/android/os/AsyncTask.html)
AsyncTask 是android 提供的轻量级异步类，使用线程池的机制，容量是128，最多同时运行5个core线程

下面一个示例代码

```java
  public class TestActivity extends Activity{

    @Override
    protected void onCreate(Bundle saveInstanceState){
      super.onCreate(saveInstanceState);
      setContentView(R.layout.main);
      (new LoadAsyncTask()).execute(1000);
    }

    private classLoadAsyncTask extends AsyncTask{
      @Override
      protected void onPreExecute(){
        Log.v("test", "start");
      }

      @Override
      protected String doInBackground(Integer...params){
        // load the http data
      }

      @Override
      protected void onPostExecute(String result){
        Log.v("test", "finish");
      }

    }

  }
```
