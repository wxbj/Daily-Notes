# 1、初识Flask
    from flask import Flask  
    app = Flask(__name__)  
    @app.route("/",methods=["GET","POST"])  
    def index():  
        return ""  
    app.run()  
# 2.Response三剑客
HTTPResponse：return "先帝创业未半而中道崩殂"  
render: return render_template("login.html")  
redirect:return redirect("/login")  
小儿子：  
    return send_file() : return send_file("1.mp4") 打开并传输文件  
    return jsonify() : return jsonify({"name":"JWB","age":73})  Content-Type: application/json  
# 3.Flask中的Request公共变量？
from flask import request  
request.method 请求方式  
request.form 存储的是所有FormData中的所有数据  
request.args 存储的是所有URL中的所有数据  
request.json Content-Type: application/json 存放在request.json中  
request.data 当Content-Type无法被解析时，存放原始数据  
request.url 请求地址  
request.path url路由地址  
request.host 主机地址  
request.host_url 将主机地址转换为httpurl  
# 4.Jinja2
{{}} 引用或执行时  
{%%} 逻辑代码  
符合python用法  
# 5.Session
from flask import session  
app.secret_key = "yinjiaodawangba"  
Flask中的session是保存在 cookie 中的  
session["user"] = "jwb"  
session.get("user")  
# 6.Flask 中的路由
        *endpoint - url_for 反向地址  
        *endpoint 默认是视图函数名  
        *methods 指定视图函数的请求方式，默认GET  
        defaults={"nid":1} 指定视图函数的默认参数  
        strict_slashes=False 是否严格遵循路由规则 /login/  
        redirect_to="/login" 永久跳转地址 301  
    
        *动态路由参数：  
        /<int:nid>  /<string:str> /<nid>   
        视图函数中需要有参数接收动态路由参数  
        
# 7.Flask中的实例化配置
        *template_folder = "temp"  # template模板目录,   默认当前项目中的 templates 目录  
        *static_folder = "jingtaiwenjianmulu" 目录  
        *static_url_path = "/static" 访问路径  
        static_host =   
        
        host_matching = False,  #   如果不是特别需要的话,慎用,否则所有的route 都需要host=""的参数  
        subdomain_matching = False,  # 理论上来说是用来限制SERVER_  NAME子域名的,但是目前还没有感觉出来区别在哪里  
        instance_path = None,  # 指向另一个Flask实例的路径  
        instance_relative_config = False  # 是否加载另一个实例的配置  
        root_path = None  # 主模块所在的目录的绝对路径,默认项目目录  
        
# 8.app对象配置
        app.config.from_object(Debug)  
        class Debug(object):  
            DEBUG=True  
# 9.蓝图 Blueprint
        form flask import Blueprint  
        blue = Blueprint("blue_id",__name__,url_prefix)  
        url_prefix 前缀  
        app.register_blueprint(blue)  
# 10.特殊装饰器：
        @app.template_global()  
        @app.template_filter()  
        
        @app.before_request  
            请求进入视图函数之前  
            
        @app.after_request  
        def af1(response)  
            return response  
            结束视图函数之后，返回客户端之前  
            
        
        正常:be1 - be2 - be3 - af3 - af2 - af1   
        异常:be1 - af3 - af2 - af1  
        
        @app.errorhandler(404) 重定义页面  
        def error404(args):  
# 11.CBV :
    from flask import views  
    
    class LoginView(views.MethodView):  
        def get(self):  
            return  
            
        def post(self):  
            return  
            
    
    app.add_url_rule("/login",endpoint=None,view_func=LoginView.as_view("login"))  
# 12.flash:
    from flask import flash,get_flash_messages  
    
    flash("","tag")  
    get_flash_messages("tag")  
# 13.Flask-Session
    from flask_session import Session  
    from flask import session  
    
    app.config["SESSION_TYPE"] = "redis"  
    app.config["SESSION_REDIS"] = Redis("127.0.0.1",6379,db=7)  
    Session(app)  
    
    session["user"] == "123"  
    session.get("user")  
    
# 14.WTForms - MoudelForm
    from wtfroms.fields import simple,core  
    from wtfroms import Form,validators  
    
    class LoginForm(Form):  
        username = simple.StringFields(  
            label = "" #看源码 __init__  
        )  
        
    
    lf = LoginForm()  
    render_template("html",lf=lf)  
    
    {{ lf.uername }}  
    {{ lf.uername.label }}  
    {{ lf.uername.errors.0 }}  
    
    lf = LoginForm(request.form)  
    
    if not lf.validata():  
        render_template("html",lf=lf)  
    
    lf.data.get("username")  
    
# 15.DBUtils 数据库连接池
    
