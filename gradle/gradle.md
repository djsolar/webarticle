### gradle 常用命令
1. gradle build 编译程序
2. gradle clean 清除工程
3. gradle help --task <task> 查看任务的详情
<pre><code> gradle -q help --task libs
Detailed task information for libs
Paths
     :api:libs
     :webapp:libs
Type
     Task (org.gradle.api.Task)
Description
     Builds the JAR</code></pre>
这些结果包含了任务的路径、类型以及描述信息等。
4. gradle properties 查看project的属性
5. gradle assemble 编译并打包 jar 文件，但不会执行单元测试。一些其他插件可能会增强这个任务的功能。例如，如果采用了 War 插件，这个任务便会为你的项目打出 War 包。
6. gradle check 编译并测试代码。一些其他插件也可能会增强这个任务的功能。例如，如果采用了 Code-quality 插件，这个任务会额外执行 Checkstyle。
7. gradle uploadArchives 发布jar包 
    <pre><code>uploadArchives {
        repositories {
            flatDir {
            dirs 'repos'
            }
        }
    }</code></pre>
8. gradle <task>... -x <task> 可以执行多个任务，并且可以排除某些任务
9. gradle cT (compileTest) 可以用驼峰命名的任务中每个单词的首字母进行调用。例如，可以执行 gradle compTest or even gradle cT 来调用 compileTest 任务。
10. gradle -q -b subdir/myproject.gradle hello调用 gradle 时，默认情况下总是会构建当前目录下的文件，可以使用-b 参数选择构建的文件，并且当你使用此参数时settings.gradle 将不会生效
11. gradle -q -p subdir hello 你可以使用 -p 参数来指定构建的目录，例如在多项目构建中你可以用 -p 来替代 -b 参数
12. gradle projects 会为你列出子项目名称列表
13. gradle -q tasks  会列出所有的任务
14. gradle -q tasks --all 执行 gradle tasks 会列出项目中所有任务。这会显示项目中所有的默认任务以及每个任务的描述, 用-all 参数来收集更多任务信息
15. gradle -q dependencies api:dependencies webapp:dependencies 会列出项目的依赖列表，所有依赖会根据任务区分，以树型结构展示出来当然你可以通过--configuration 参数来查看 指定构建任务的依赖情况 gradle -q api:dependencies --configuration testCompile
16. gradle -q api:properties 可以查看指定项目的所有的属性
17. 
