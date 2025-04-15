# This is a title, em, or, header
### h3 example
this this the example of content
#### how h4 look like?
###### seems h6 is the mallest

### let's add a picture
![this is a test pic](https://img-s.msn.cn/tenant/amp/entityid/BB1msOZc?w=0&h=0&q=60&m=6&f=jpg&u=t)

### let's add some code
``` HTML

<!-- 模态框 -->
<div class="modal fade" id="myModal">
  <div class="modal-dialog">
    <div class="modal-content">

      <!-- 模态框头部 -->
      <div class="modal-header">
        <h4 class="modal-title">模态框标题</h4>
        <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
      </div>

      <!-- 模态框内容 -->
      <div class="modal-body">
        模态框内容..
      </div>

      <!-- 模态框底部 -->
      <div class="modal-footer">
        <button type="button" class="btn btn-danger" data-bs-dismiss="modal">关闭</button>
      </div>

    </div>
  </div>
</div>
```

``` python
def verify_cookie():
    token = request.cookies.get('auth_token')
    if not token:
        return False, "未检查到登录状态"
    try:
        
        data = jwt.decode(token, app.config['SECRET_KEY'], algorithms=['HS256'])
        response = cache.get(f"usercookie_{data['userID']}")
        #print(f"接受token: " + token)
        #print(f"储存token：" + response if (response) else "None")
        if (response and response!=token): # 验证用户登录状态
            return False, "你已在其他设备登录"
        if (not response):
            cache.set(f"usercookie_{data['userID']}", token)
        return True, data['userID']  # 验证成功，返回用户ID
    except jwt.ExpiredSignatureError:
        return False, "登录状态已过期"
    except jwt.InvalidTokenError:
        return False, "登录状态不合法"
```

``` C++
while ((entry = readdir(dir)) != nullptr) {
        // 跳过目录本身和上级目录
        if (entry->d_name[0] == '.' && (entry->d_name[1] == '\0' || (entry->d_name[1] == '.' && entry->d_name[2] == '\0'))) {
            continue;
        }

        string fileName = entry->d_name;
        string imagePath = folderPath + "/" + fileName;

        // 检查文件扩展名，只处理常见图像文件
        string lowerFileName = fileName;
        transform(lowerFileName.begin(), lowerFileName.end(), lowerFileName.begin(), ::tolower);
        if (lowerFileName.find(".jpg") == string::npos &&
            lowerFileName.find(".jpeg") == string::npos &&
            lowerFileName.find(".png") == string::npos) {
            continue;
        }

        EXIFInfo exifData;
        extractExifInfo(imagePath, exifData);

        // 写入CSV行
        csvFile << "\"" << fileName << "\","
                << "\"" << exifData.Copyright << "\","
                << "\"" << exifData.Software << "\","
                << "\"" << exifData.ImageDescription << "\","
                << "\"" << exifData.DateTime << "\","
                << "\"" << exifData.Make << "\","
                << "\"" << exifData.Model << "\"\n";
    }
```
