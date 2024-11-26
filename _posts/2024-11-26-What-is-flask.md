---
title: flask란 무엇인가?
author: alpa28980
date: Tue, 26 Nov 2024 01:28:44 GMT
categories: ["Program Language"]
tags: ["flask"]
comment: true
---

서론
--

Flask는 파이썬 기반의 경량 웹 프레임워크입니다. Flask는 웹 애플리케이션 개발을 쉽고 빠르게 시작할 수 있도록 설계되었으며, 동시에 복잡한 애플리케이션으로 확장할 수 있는 유연성도 가지고 있습니다.

Flask의 주요 특징으로는 Application Context와 Request Context 제공, Blueprints를 통한 모듈화 및 확장성 지원, 다양한 Extension 제공, Command Line Interface, 내장 개발 서버, 대화형 Python 쉘 등이 있습니다. 이러한 특징들은 개발 편의성과 생산성을 높여주며, 애플리케이션의 구조화와 기능 확장을 용이하게 합니다 .

경량 프레임워크로서 Flask는 간단한 코드 구조와 작은 메모리 사용량으로 개발 진입 장벽이 낮습니다. 또한 필요한 기능만 추가하는 방식으로 애플리케이션을 유연하게 구성할 수 있습니다. 따라서 Flask는 프로토타입 개발이나 작은 규모의 프로젝트에 적합하지만 , 동시에 대규모 프로젝트에도 확장이 가능합니다 .

Flask의 구조 - 기본 구조
-----------------

Flask 애플리케이션의 기본 구조는 다음과 같은 핵심 요소들로 구성됩니다.

1.  애플리케이션 객체(app) Flask 애플리케이션은 Flask 클래스의 인스턴스인 app 객체를 중심으로 구성됩니다. 이 객체는 애플리케이션의 모든 구성 요소와 동작을 관리합니다.

python

    from flask import Flask
    app = Flask(__name__)
    

2.  블루프린트(Blueprint) 복잡한 애플리케이션의 경우 기능별로 모듈화하여 관리할 수 있습니다. 블루프린트를 통해 라우팅, 뷰 함수, 정적 파일 등을 그룹화하고 app에 등록할 수 있습니다.

python

    from flask import Blueprint
    bp = Blueprint('blog', __name__)
    

3.  라우팅(Routing)과 뷰 함수(View Function) 라우팅은 URL과 해당 URL에 대한 처리 로직인 뷰 함수를 매핑합니다. 뷰 함수에서는 요청을 처리하고 응답을 생성합니다.

python

    @app.route('/')
    def index():
        return 'Hello, World!'
    

4.  요청(Request)과 응답(Response) 요청 객체(request)에는 클라이언트로부터 전송된 데이터(URL 파라미터, 폼 데이터, 파일 등)가 저장됩니다. 응답 객체(response)는 클라이언트에 전송할 데이터를 포함합니다.
    
5.  템플릿(Template) 렌더링 Flask는 Jinja2 템플릿 엔진을 사용하여 동적인 HTML 페이지를 생성합니다. 템플릿에 데이터를 전달하여 렌더링할 수 있습니다.
    
6.  세션(Session) 세션을 통해 클라이언트의 상태 정보를 서버에 저장하고 관리할 수 있습니다. 로그인 인증, 장바구니 등에 활용됩니다.
    

이와 같이 Flask 애플리케이션은 위의 핵심 요소들이 유기적으로 연동되어 웹 애플리케이션의 기능을 제공합니다.

Flask의 구조 - 라우팅과 뷰 함수
---------------------

Flask에서 라우팅은 @app.route 데코레이터를 사용하여 URL 패턴과 해당 URL을 처리할 뷰 함수를 연결합니다. 예를 들어 다음과 같이 라우팅을 정의할 수 있습니다:

python

    @app.route('/')
    def index():
        return 'Hello, World!'
    
    @app.route('/about')
    def about():
        return 'About Page'
    

위 코드에서 '/'는 기본 URL이며, 이 URL에 대한 요청이 들어오면 index() 함수가 실행됩니다. '/about' URL에 대한 요청은 about() 함수가 처리합니다.

뷰 함수는 클라이언트 요청을 처리하고 응답을 생성하는 역할을 합니다. 요청 객체(request)를 통해 URL 파라미터, 폼 데이터, 파일 등의 데이터에 접근할 수 있습니다. 응답 객체(response)에는 클라이언트에 전송할 데이터가 포함됩니다. 다음은 간단한 뷰 함수 예시입니다:

python

    @app.route('/user/<username>')
    def show_user(username):
        # 데이터베이스에서 사용자 정보 조회
        user = get_user_by_name(username)
        if user:
            # 사용자 정보를 HTML 템플릿에 렌더링하여 응답
            return render_template('user.html', user=user)
        else:
            # 404 에러 응답
            abort(404)
    

위 코드에서 show\_user() 함수는 URL에서 전달된 username 파라미터를 사용하여 데이터베이스에서 사용자 정보를 조회합니다. 사용자 정보가 있으면 user.html 템플릿에 렌더링하여 응답하고, 없으면 404 에러를 반환합니다.

Flask의 구조 - 템플릿
---------------

Flask에서는 Jinja2 템플릿 엔진을 사용하여 동적인 웹 페이지를 생성합니다. 템플릿은 HTML 마크업 언어와 Jinja2의 구문을 혼합하여 작성되며, 서버에서 렌더링되어 HTML 문자열로 변환됩니다.

Jinja2는 다음과 같은 주요 기능을 제공합니다:

*   템플릿 상속: 기본 레이아웃을 정의하고 하위 템플릿에서 상속받아 콘텐츠를 삽입할 수 있습니다. 이를 통해 코드 중복을 피하고 일관된 레이아웃을 유지할 수 있습니다.
*   필터: 데이터를 원하는 형식으로 변환하거나 조작할 수 있습니다. 예를 들어 문자열을 대문자로 변환하거나 날짜 형식을 변경할 수 있습니다.
*   매크로: 재사용 가능한 코드 조각을 정의하고 템플릿 내에서 호출할 수 있습니다.
*   컨텍스트 프로세서: 템플릿에서 사용할 수 있는 변수를 정의할 수 있습니다.

Flask 애플리케이션에서 render\_template 함수를 사용하여 템플릿을 렌더링합니다. 이 함수에는 템플릿 파일 경로와 렌더링할 데이터를 전달합니다. 예를 들어:

python

    from flask import render_template
    
    @app.route('/')
    def index():
        user = {'name': 'John Doe'}
        return render_template('index.html', user=user)
    

위 코드에서 index.html 템플릿이 렌더링되며, user 객체가 템플릿에 전달됩니다. 템플릿에서는 {{ user.name }} 구문을 사용하여 데이터에 접근할 수 있습니다.

Jinja2의 구문을 사용하면 조건문, 반복문, 필터, 매크로 등을 활용하여 동적인 웹 페이지를 생성할 수 있습니다. 템플릿 상속을 통해 코드 중복을 피하고 일관된 레이아웃을 유지할 수 있습니다 .

Flask의 주요 기능 - 요청 처리
--------------------

Flask에서는 요청 객체(request)를 통해 클라이언트로부터 전송된 데이터를 처리할 수 있습니다. 요청 객체에는 URL 파라미터, 폼 데이터, 파일 등의 정보가 포함되어 있습니다.

GET 요청의 경우, URL 파라미터에 포함된 데이터에 접근할 수 있습니다:

python

    from flask import request
    
    @app.route('/user')
    def get_user():
        username = request.args.get('username')
        # 사용자 이름으로 처리 로직 수행
        ...
    

POST 요청의 경우, 폼 데이터나 JSON 데이터를 처리할 수 있습니다:

python

    @app.route('/login', methods=['POST'])
    def login():
        username = request.form.get('username')
        password = request.form.get('password')
        # 로그인 처리 로직 수행
        ...
    

python

    @app.route('/api/users', methods=['POST'])
    def create_user():
        user_data = request.get_json() # JSON 데이터 수신
        # 사용자 생성 로직 수행
        ...
    

요청 객체의 주요 속성과 메서드는 다음과 같습니다:

*   request.args: URL 쿼리 스트링에 포함된 파라미터 값
*   request.form: POST 요청의 폼 데이터
*   request.files: 업로드된 파일
*   request.headers: 요청 헤더
*   request.method: 요청 메서드(GET, POST 등)
*   request.get\_json(): JSON 데이터 파싱

이처럼 Flask에서는 요청 객체를 사용하여 다양한 유형의 요청 데이터를 쉽게 처리할 수 있습니다 .

Flask의 주요 기능 - 세션 관리
--------------------

Flask에서는 세션 객체(session)를 통해 클라이언트의 상태 정보를 서버에 저장하고 관리할 수 있습니다. 로그인 인증, 장바구니 등 다양한 기능에서 활용됩니다.

세션 데이터는 일반적으로 서버의 파일 시스템이나 메모리, 데이터베이스 등에 저장됩니다. Flask에서는 세션 데이터를 쿠키에 직렬화된 형태로 저장하여 클라이언트와 주고받습니다. 이때 세션 데이터는 암호화되어 보안이 유지됩니다.

python

    from flask import Flask, session
    
    app = Flask(__name__)
    app.secret_key = 'super_secret_key' # 세션 암호화를 위한 키 설정
    
    @app.route('/set_session')
    def set_session():
        session['username'] = 'john_doe' # 세션에 데이터 저장
        return 'Session set'
    
    @app.route('/get_session')
    def get_session():
        username = session.get('username', 'Guest') # 세션에서 데이터 조회
        return f'Username: {username}'
    

위 예제에서 세션 데이터를 저장하고 조회하는 방법을 보여줍니다. app.secret\_key를 통해 세션 암호화 키를 설정하고, session 객체를 사용하여 데이터를 저장하고 읽습니다.

Flask에서는 세션 수명 관리를 위한 옵션도 제공합니다. permanent 속성을 True로 설정하면 세션 쿠키의 만료 시간을 클라이언트가 종료될 때까지로 연장할 수 있습니다. 또한 SESSION\_COOKIE\_SAMESITE 설정을 통해 CSRF 공격을 방지할 수 있습니다.

Flask의 주요 기능 - 데이터베이스 연동
------------------------

Flask에서는 SQLite나 SQLAlchemy를 사용하여 데이터베이스를 연동할 수 있습니다. SQLite는 파일 기반의 경량 데이터베이스로, 개발 및 테스트 환경에서 주로 사용됩니다. SQLAlchemy는 Python의 ORM(Object-Relational Mapping) 라이브러리로, 다양한 데이터베이스와 연동하여 객체 지향 방식으로 데이터를 처리할 수 있습니다.

SQLAlchemy를 사용하여 데이터베이스 모델을 정의하고 CRUD 작업을 수행할 수 있습니다. 먼저 Flask-SQLAlchemy 확장 패키지를 설치합니다.

    pip install flask-sqlalchemy
    

그리고 Flask 애플리케이션에서 SQLAlchemy를 초기화합니다.

python

    from flask import Flask
    from flask_sqlalchemy import SQLAlchemy
    
    app = Flask(__name__)
    app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///db.sqlite'
    db = SQLAlchemy(app)
    

데이터베이스 모델은 SQLAlchemy의 모델 클래스를 상속받아 정의합니다.

python

    from .models import db
    
    class User(db.Model):
        id = db.Column(db.Integer, primary_key=True)
        username = db.Column(db.String(80), unique=True, nullable=False)
        email = db.Column(db.String(120), unique=True, nullable=False)
    
        def __repr__(self):
            return f'<User {self.username}>'
    

이렇게 정의된 모델을 통해 데이터베이스의 CRUD 작업을 수행할 수 있습니다. 예를 들어 사용자를 추가하고 조회하는 코드는 다음과 같습니다.

python

    from .models import User, db
    
    # 사용자 추가
    user = User(username='john_doe', email='john@example.com')
    db.session.add(user)
    db.session.commit()
    
    # 사용자 조회
    user = User.query.filter_by(username='john_doe').first()
    print(user.username, user.email) # john_doe john@example.com
    

이처럼 Flask에서는 SQLAlchemy ORM을 사용하여 데이터베이스 모델을 정의하고 CRUD 작업을 수행할 수 있습니다. SQLite나 다른 데이터베이스도 SQLAlchemy를 통해 손쉽게 연동할 수 있습니다 .

Flask의 주요 기능 - 정적 파일 제공
-----------------------

Flask에서는 정적 파일(CSS, JavaScript, 이미지 등)을 제공하기 위해 프로젝트 내에 `static` 폴더를 만듭니다. 이 폴더는 Flask 애플리케이션의 루트 디렉토리에 위치해야 합니다. 정적 파일을 제공하려면 app.py 파일에서 다음과 같이 `static_folder` 매개변수를 사용하여 등록해야 합니다:

python

    from flask import Flask
    
    app = Flask(__name__, static_folder='static')
    

이제 정적 파일에 접근할 수 있는 URL을 생성하려면 `url_for` 함수를 사용합니다 . 예를 들어 `/static/css/styles.css` 파일의 URL은 다음과 같이 생성할 수 있습니다:

python

    from flask import url_for
    
    css_url = url_for('static', filename='css/styles.css')
    

템플릿에서 정적 파일의 URL을 사용하려면 다음과 같이 합니다:

html

    <link rel="stylesheet" href="{{ url_for('static', filename='css/styles.css') }}">
    

정적 파일을 제공할 때는 캐싱을 적절히 설정하는 것이 중요합니다. Flask는 정적 파일을 캐싱하기 위한 기본 설정을 제공하지만, 프로덕션 환경에서는 더 나은 성능을 위해 웹 서버에서 정적 파일을 직접 제공하는 것이 좋습니다 .

Flask의 주요 기능 - 확장 기능
--------------------

Flask는 핵심 기능 외에도 다양한 확장 기능을 제공하여 개발자가 필요에 따라 기능을 추가할 수 있습니다. 주요 확장 기능으로는 다음과 같은 것들이 있습니다:

*   Flask-SQLAlchemy: SQLAlchemy ORM을 사용하여 데이터베이스와 연동할 수 있습니다.
*   Flask-Login: 사용자 인증 시스템을 구축할 수 있습니다.
*   Flask-WTF: WTForms 라이브러리를 활용하여 폼 처리를 간소화할 수 있습니다.
*   Flask-Mail: 이메일 발송 기능을 제공합니다.
*   Flask-Migrate: SQLAlchemy 데이터베이스 마이그레이션을 지원합니다.
*   Flask-Caching: 캐싱 기능을 제공하여 애플리케이션 성능을 향상시킵니다.

이러한 확장 기능들은 pip를 통해 설치할 수 있습니다. 예를 들어 Flask-SQLAlchemy를 설치하려면 다음 명령을 실행합니다:

    pip install flask-sqlalchemy
    

그리고 Flask 애플리케이션에서 확장 기능을 초기화하고 사용할 수 있습니다. 예를 들어 Flask-SQLAlchemy를 사용하려면 다음과 같이 할 수 있습니다:

python

    from flask import Flask
    from flask_sqlalchemy import SQLAlchemy
    
    app = Flask(__name__)
    app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///db.sqlite'
    db = SQLAlchemy(app)
    
    class User(db.Model):
        id = db.Column(db.Integer, primary_key=True)
        username = db.Column(db.String(80), unique=True)
    
        def __repr__(self):
            return f'<User {self.username}>'
    

위 코드에서는 SQLAlchemy를 초기화하고, User 모델을 정의하였습니다. 이후 데이터베이스 CRUD 작업을 수행할 수 있습니다 .

이처럼 Flask는 다양한 확장 기능을 제공하여 개발자가 필요한 기능을 쉽게 추가할 수 있도록 합니다. 확장 기능을 활용하면 보다 풍부한 기능을 가진 웹 애플리케이션을 구축할 수 있습니다.

Flask의 장단점
----------

Flask의 주요 장점은 경량성과 확장성입니다. Flask는 마이크로 웹 프레임워크로서 가벼운 구조를 가지고 있어 개발 진입 장벽이 낮고 초기 개발 속도가 빠릅니다. 또한 필요한 기능만 선택적으로 추가할 수 있어 애플리케이션을 유연하게 구성할 수 있습니다. 이는 프로토타입 개발이나 작은 규모의 프로젝트에 적합합니다 . 또한 Blueprints와 Extensions 기능을 통해 대규모 프로젝트에도 확장이 가능합니다 .

그러나 Flask의 단점으로는 대규모 프로젝트에 부적합할 수 있다는 점과 보안 이슈 가능성이 있습니다. 마이크로 프레임워크로서 대규모 프로젝트를 위한 기능이 부족할 수 있으며, 보안 기능도 직접 구현해야 하는 번거로움이 있습니다. 또한 다른 프레임워크에 비해 상대적으로 작은 커뮤니티로 인해 지원이 부족할 수 있습니다 .

따라서 Flask는 프로토타입 개발이나 작은 규모의 프로젝트에 적합하지만, 대규모 프로젝트의 경우 다른 프레임워크를 고려해볼 필요가 있습니다. 또한 보안 문제에 대해서는 개발자가 직접 대책을 마련해야 합니다. 하지만 경량성과 확장성으로 인해 Flask는 여전히 많은 개발자들에게 인기 있는 웹 프레임워크입니다.

결론
--

Flask는 경량성과 확장성이라는 두 가지 핵심 특징을 가지고 있습니다. 마이크로 웹 프레임워크로서 간단한 코드 구조와 작은 메모리 사용량을 바탕으로 초기 개발 진입 장벽이 낮고, 필요한 기능만 추가하는 방식으로 애플리케이션을 유연하게 구성할 수 있습니다 . 또한 Blueprints 기능을 통해 대규모 프로젝트로의 확장도 용이합니다 .

Flask는 프로토타입 개발이나 작은 규모의 프로젝트에 주로 활용되고 있습니다. 하지만 확장성 있는 구조 덕분에 대규모 웹 서비스 개발에도 사용되고 있습니다. 예를 들어 Netflix나 Reddit 등의 서비스가 Flask를 사용하고 있습니다 .

앞으로 Flask는 Python 생태계 내에서 지속적으로 발전할 것으로 전망됩니다. 특히 머신러닝, 데이터 분석 등 다양한 분야에서 Python의 활용도가 높아짐에 따라 Flask의 수요도 더욱 증가할 것으로 보입니다. 또한 클라우드 기반 서버리스 애플리케이션 개발에 Flask가 적합한 프레임워크로 주목받고 있습니다.

요약하면 Flask는 경량성과 확장성을 바탕으로 다양한 규모의 웹 애플리케이션 개발에 유용하게 사용되고 있는 파이썬 웹 프레임워크입니다. 프로토타입 개발부터 대규모 서비스까지 적용 범위가 넓으며, 앞으로 Python의 영향력 확대와 함께 Flask의 활용도 역시 더욱 높아질 것으로 기대됩니다.

---
---

<iframe src="https://ads-partners.coupang.com/widgets.html?id=807239&template=carousel&trackingCode=AF3190673&subId=&width=680&height=140&tsource=" style="width:100%" height="140" frameborder="0" scrolling="no" referrerpolicy="unsafe-url" browsingtopics></iframe>
해당 링크를 통해 제품 구매가 이루어진 경우 쿠팡 파트너스 활동 일환으로 인해 일정 수수료가 블로거에게 제공되고 있습니다

