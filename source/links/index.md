---
title: 友情链接
date: 2025-07-13 21:16:15
banner: true
type: links
data: links
---

## 友情链接申请

{% fold '✅ 友链相关须知' %}

## 你提交的信息有可能被修改

1. 为了友链相关页面和组件的统一性和美观性，可能会对你的昵称进行缩短处理，例如昵称包含博客、XX的XX等内容或形式将被简化。
2. 为了图片加载速度和内容安全性考虑，头像实际展示图片均使用博客自己图床，所以无法收到贵站自己的头像更新，如果有迫切的更改信息需求，请在本页的评论中添加。

## 友情链接曝光

本站注重每一个友情链接的曝光，如果你在意本站给贵站提供的曝光资源，那么你可能在以下地方看到贵站。

## 页脚每次刷新会随机展示3个友情链接

1. 页脚「更多」链接跳转到友链页面
2. 导航栏「友链」分组中跳转到「友情链接」查看所有友情链接
3. 导航栏「友链」分组中跳转到「宝藏博主」随机跳转到一个友情链接

### 友情链接页面日UV平均在20左右。

## 关于推荐分类

推荐分类包含参与本站开发、提供设计灵感、捐助本站的优秀博主。

{% endfold %}

1. 网站名称：<code>小萌虎</code>
2. 网站描述：<code>分享设计与科技生活</code>
3. 网站地址：<code>https://blog.hallobo.xin</code>
4. 网站头像：<code>https://bu.dusays.com/2025/10/01/68dcb6bce89aa.jpg</code>
5. 网站封面：<code>https://bu.dusays.com/2025/10/01/68dcb6bce89aa.jpg</code>

<p>请<strong>勾选</strong>你符合的条件：</p>

<div id="friendlink_checkboxs">
<p>
  <label><input type="checkbox" id="checkbox1" onclick="checkForm()">我已添加 <b>小萌虎</b> 博客的友情链接</label>
</p>
<p>
  <label><input type="checkbox" id="checkbox2" onclick="checkForm()">我的链接主体为 <b>个人</b>，网站类型为<b>博客</b></label>
</p>
<p>
  <label><input type="checkbox" id="checkbox3" onclick="checkForm()">我的网站现在可以在中国大陆区域正常访问</label>
</p>
<p>
  <label><input type="checkbox" id="checkbox4" onclick="checkForm()">网站内容符合中国大陆法律法规</label>
</p>
</div>

<div class="friendlink-actions">
  <button id="btnCreateFriendlink" disabled="">创建新友情链接</button>
  <button id="btnModifyFriendlink" disabled="">修改已有友情链接</button>
</div>

<style>
        .tk-submit {
            opacity: 0;
            height: 0;
            transition: opacity 0.5s, height 0.5s;
      overflow: inherit!important;
        }

    .tk-comments-container .tk-submit {
      opacity: 1;
            height: auto;
      overflow: inherit!important;
    }

    #friendlink_checkboxs input {
      margin-right: 4px;
    }

    .friendlink-actions {
      margin: 12px 0 0 0;
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
    }

    .friendlink-actions button {
      padding: 8px 16px!important;
      border-radius: 8px!important;
      border: 1px solid rgba(0,0,0,.1);
      background: var(--heo-theme, #409eff);
      color: #fff;
      cursor: pointer;
      transition: opacity .2s ease, filter .2s ease;
    }

    #btnCreateFriendlink {
      background: var(--heo-red);
    }

    .friendlink-actions button[disabled] {
      opacity: .5;
      cursor: not-allowed;
      filter: grayscale(40%);
    }
</style>

<script> 
    // 等待 DOM 加载完成后再执行
    document.addEventListener('DOMContentLoaded', function() {
        var twikooSubmit = document.getElementsByClassName("tk-submit")[0];
        if (twikooSubmit) {
            twikooSubmit.style.opacity = "0";
            twikooSubmit.style.height = "0";
            twikooSubmit.style.overflow = "hidden";
        }

        // 绑定按钮事件
        var btnCreate = document.getElementById('btnCreateFriendlink');
        var btnModify = document.getElementById('btnModifyFriendlink');

        function setTextareaValue(text) {
            var input = document.getElementsByClassName('el-textarea__inner')[0];
            if (!input) return;
            let evt = document.createEvent('HTMLEvents');
            evt.initEvent('input', true, true);
            input.value = text;
            input.dispatchEvent(evt);
            input.focus();
            input.setSelectionRange(-1, -1);
        }

        function waitForElement(selector, timeout) {
            return new Promise(function(resolve, reject) {
                var timer = 0;
                var interval = setInterval(function() {
                    var el = document.querySelector(selector);
                    if (el) {
                        clearInterval(interval);
                        clearTimeout(timer);
                        resolve(el);
                    }
                }, 100);
                timer = setTimeout(function() {
                    clearInterval(interval);
                    reject(new Error('Element not found: ' + selector));
                }, timeout || 5000);
            });
        }

        function showCommentBox() {
            var twikooSubmitLocal = document.getElementsByClassName('tk-submit')[0];
            if (twikooSubmitLocal) {
                twikooSubmitLocal.style.opacity = '1';
                twikooSubmitLocal.style.height = 'auto';
                twikooSubmitLocal.style.overflow = 'auto';
            }
        }

        var createTemplate = '网站名称：\n网站地址：\n网站头像：\n网站描述：\n网站类型:';

        var modifyTemplate = '原地址：\n新地址：\n新图片：\n新描述：\n新类型：';

        if (btnCreate) {
            btnCreate.addEventListener('click', function() {
                showCommentBox();
                waitForElement('.el-textarea__inner', 8000).then(function() {
                    setTextareaValue(createTemplate);
                }).catch(function() {});
            });
        }
        if (btnModify) {
            btnModify.addEventListener('click', function() {
                showCommentBox();
                waitForElement('.el-textarea__inner', 8000).then(function() {
                    setTextareaValue(modifyTemplate);
                }).catch(function() {});
            });
        }
    });

    function checkForm() {
        var checkbox1 = document.getElementById("checkbox1");
        var checkbox2 = document.getElementById("checkbox2");
        var checkbox3 = document.getElementById("checkbox3");
        var checkbox4 = document.getElementById("checkbox4");
        var twikooSubmit = document.getElementsByClassName("tk-submit")[0];
        var btnCreate = document.getElementById('btnCreateFriendlink');
        var btnModify = document.getElementById('btnModifyFriendlink');
        
        var allChecked = checkbox1.checked && checkbox2.checked && checkbox3.checked && checkbox4.checked;
        
        // 勾选只控制按钮启用状态，不再直接显示评论区
        if (btnCreate && btnModify) {
            btnCreate.disabled = !allChecked;
            btnModify.disabled = !allChecked;
        }

        // 若取消勾选则隐藏提交按钮
        if (twikooSubmit && !allChecked) {
            twikooSubmit.style.opacity = "0";
            twikooSubmit.style.height = "0";
            twikooSubmit.style.overflow = "hidden";
        }
    }
</script>