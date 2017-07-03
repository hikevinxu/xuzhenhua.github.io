---
title: git
date: 2017-07-03 08:44:57
tags:
---
##1. git  init         ------初始化git


##2. git config --global user.name "hua"   ------- 配置用户名


##3.git config --global user.email "hua@qq.com"        ------------配置用户邮箱


##4. git config --list           查看用户信息


##5.git add ./demo.txt


##6.git commit -m "hello,完成了第一个功能"


##7.当输入git commit 然后回车 会报错，这时我们可以按esc键+ :q 键 退出，如果在上面输入了信息，我们可以按esc键+ :q!键强制退出；


##8.git  status  ：查看现在的状态


##9. git add . 或 git add ./    ------表示把工作区的所有文件提交到暂存库

##10 git commit --all  -m  “说明信息”        -------表示吧暂存库的所有文件提交到版本库

##11.git log  查看之前的保存的版本

##12.git log --oneline   一行显示之前的版本

##13. 回退 ； git reset --hard  Head～0，1，2，3     回退到什么状态

##14. git branch dev  -----创建一个名字为dev的分支

##15 git branch     -------查看分支

##16. git checkout  dev   ----切换到dev分支

##17. git meger dev    合并分支 

##18. git push  https://。。。。。。。   -----上传到github

##19 git pull http://.......         --------下载到本地(需要新建一个仓库)

##20.git clone https:// .......               -------下载到本地(不需要新建一个仓库)


##21. ssh-keygen -t rsa -C "youxiangdizhi@qq.com"  回车 回车 回车  一路回车

##22. gulp 操作 ：
  ###执行一次压缩一共分为5步：
    ###1. 初始化配置：
      a. 通过nmp下载安装全局gulp  ： npm install gulp-cli -g;  （安装全局gulp安装一次即可）;
      b. 在项目文件夹下下载安装gulp ： npm install gulp --save ;
        (不同项目文件夹下都要安装);
    ###2.在当前项目中新建一个文件: gulpfile.js

    ###3.下载要使用的方法：
      npm install gulp-uglify --save  ;
      npm install gulp-concat  --save ;
    ###4.引用要使用的方法：
      var gulp =  require('gulp');
      var uglify =  require('gulp-uglify');
      var concat =  require('gulp-concat');
    ###5.在函数中使用这些方法： 
      gulp.task('script',function(){    -----创建一个任务，任务名是script
          gulp.src(["./app.js","./sign.js"])  
           ------指定想要处理的文件，如果有两个或两个以上的文件合并 ，用中括号包起来
            .pipe(concat('index.js'))    ------ 合并成一个文件，参数是合并后的文件名
            .pipe(uglify())          --------压缩文件
            .pipe(gulp.dest("./dist"))    --------指定最终处理后的文件的存放路径
      })

    ###6. 在cmd命令行执行任务script   ：  gulp  script   格式： gulp  任务名