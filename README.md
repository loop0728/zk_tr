# zk_tr
Multi-languagesupport.

# zk_language
zk_language 是source code，主要演示多国语言的切换。
可通过菜单创建多国语言文件。选择 文件->新建->Flythings多语言翻译文件，在弹出窗口中有四种语言可选，包含中，英，日，韩。
选中需要支持的语言点击完成后，在工程下面会出现 i18n 目录，该目录下有刚才添加的语言对应的tr文件：
中文 zh_CN.tr 英文 en_US.tr 日文 ja_JP.tr 韩文 ko_KR.tr。用户也可以在这个目录新建文件，支持指定的语言。
案例除默认支持的4国语言外，还添加了法语，俄文，西班牙文，在 i18n 目录下新建文件 fr_FR-法语.tr es_ES-西班牙文.tr ru_RU-俄文.tr。

根据控件的显示内容，编辑tr文件。例如：
en_US.tr
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string name="hello_world">Hello world!</string>
    <string name="text">Text</string>
    <string name="video">Video</string>
    <string name="audio">Audio</string>
    <string name="net">Net</string>
    <string name="ip_camera">IP Camera</string>
    <string name="progressbar">Progress Bar</string>
</resources>

fr_FR-法语.tr
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string name="hello_world">Salut, le monde!</string>
    <string name="text">Texte</string>
    <string name="video">Vidéo</string>
    <string name="audio">Audio</string>
    <string name="net">Réseau</string>
    <string name="ip_camera">Caméra IP</string>
    <string name="progressbar">Barre de progression</string>
</resources>

多国语言要能正常显示，除了需要创建tr文件，还需要字库的支持。案例中使用了android的字库 DroidSansFallback.ttf，该字库包含了案例中用到的语言。用户在创建自己的应用时需根据需要选择字库。

# customer
customer 是app的运行环境。包含 bin，etc，lib，res和demo.sh。
将bin下面的zkgui, lib目录, res目录, demo.sh拷贝至板子/customer目录下；
将etc目录下内容拷贝至板子/etc目录下；
检查/config/fbdev.ini的宽高和length的设置，默认是800，480，4096.

注意：此Sample与其它zkgui Sample的libeasyui.so和字库，res/lang, res/internal/lang都有差异，验证多语言支持的功能请使用此案例下的customer作为基础的运行环境。

# 编译运行
在IDE中编译工程，导出生成文件。生成的libzkgui.so和ui替换/customer/lib/libzkgui.so, /customer/res/ui。生成的tr下的文件放置到/customer/res/lang下。


