### 创建项目
先开启创建新项目的操作，在创建的过程中，从中找到“Empty Activity”这个选项并进行选择就可以了。

### 创建项目布局
- CameraX PreviewView，其重要功能在于能够为用户提供相机图片以及视频的预览服务，方便提前查看拍摄效果。
- 设有用于把控图片拍摄的标准按钮，有了它，用户就能便捷地启动图片拍摄流程了。
- 还有专门用于开启或者结束视频拍摄的标准按钮，以此来灵活管控视频拍摄的起始与停止状态。
- 同时具备用于放置上述两个按钮的垂直指南，确保按钮在布局上更规整有序。

### 编写 MainActivity.kt 代码
以下是稍作变化后的代码示例，不过本质上和之前的功能逻辑是类似的，你可以根据实际情况进一步去细致调整哦。

```kotlin
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        
        // 通过 findViewById 方法获取用于控制图片拍摄的按钮对象
        val pictureButton = findViewById<Button>(R.id.take_picture_button)
        // 同样通过 findViewById 方法获取用于开始/停止视频拍摄的按钮对象
        val videoButton = findViewById<Button>(R.id.video_record_button)
        
        pictureButton.setOnClickListener {
            // 此处可以添加具体实现图片拍摄功能的逻辑代码，例如调用相机相关API来执行拍照操作等
        }
        
        videoButton.setOnClickListener {
            // 根据按钮当前所处状态（是开始还是停止状态）去执行对应的视频拍摄相关逻辑，
            // 例如若为开始状态，就调用启动视频拍摄的对应方法，要是处于停止状态，就调用停止拍摄的方法等
        }
    }
}
```

要记得确保在对应的布局文件里面，相关按钮的 `id` 等属性都已经准确地设置好了，而且像涉及相机操作等的功能代码也要进行合理配置，充分考虑并妥善处理好可能出现的各种异常情况，这样才能保障整个应用程序稳定且正常地运行呀。 
