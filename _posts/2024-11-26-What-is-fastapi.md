---
title: fastapi란 무엇인가?
author: alpa28980
date: Tue, 26 Nov 2024 01:12:57 GMT
categories: ["Program Language"]
tags: ["fastapi"]
comment: true
---

서론
--

FastAPI는 Python 기반의 웹 프레임워크로, 현대적이고 고성능의 API 개발을 가능하게 합니다. 이 프레임워크는 표준 Python 타입 힌트를 활용하여 API를 빠르고 쉽게 구축할 수 있습니다.

FastAPI를 배우고 사용해야 하는 주요 이유로는 다음과 같은 특징들이 있습니다:

*   매우 빠른 성능: Node.js와 Go 수준의 뛰어난 성능을 제공합니다 .
*   개발 생산성 향상: 기능 개발 속도를 약 200~300% 높일 수 있습니다 .
*   적은 버그: 개발자 실수로 인한 버그를 약 40% 줄일 수 있습니다 .
*   직관적이고 쉬운 사용법: 편집기 지원과 자동 완성 기능이 뛰어나 디버깅 시간을 줄일 수 있습니다 .
*   간결한 코드: 코드 중복을 최소화하고 파라미터 선언으로 다양한 기능을 구현할 수 있습니다 .
*   강력한 데이터 검증: Pydantic 라이브러리를 통해 강력한 데이터 검증이 가능합니다 .
*   자동 대화형 API 문서화: OpenAPI 명세를 자동으로 생성하여 API 문서화가 쉽습니다 .

위와 같은 특징들을 통해 FastAPI는 Python 개발자들이 현대적이고 실용적인 API를 빠르고 생산적으로 개발할 수 있도록 도와줍니다.

FastAPI의 기본 기능 - API 생성 및 라우팅
-----------------------------

FastAPI를 사용하여 API를 생성하고 라우팅하는 방법은 매우 간단합니다. 먼저 FastAPI 인스턴스를 생성합니다.

python

    from fastapi import FastAPI
    
    app = FastAPI()
    

그 다음 API 엔드포인트를 정의하는 함수를 작성합니다. 이때 `@app.get()`, `@app.post()` 등의 데코레이터를 사용하여 HTTP 메서드와 URL 경로를 지정할 수 있습니다.

python

    @app.get("/")
    def read_root():
        return {"message": "Hello, FastAPI!"}
    
    @app.get("/items/{item_id}")
    def read_item(item_id: int, q: str = None):
        return {"item_id": item_id, "q": q}
    

위 예제에서는 `"/"` 경로에 대한 GET 요청을 처리하는 `read_root` 함수와 `"/items/{item_id}"` 경로에 대한 GET 요청을 처리하는 `read_item` 함수를 정의했습니다. 함수 파라미터에서 타입 힌트를 사용하면 자동으로 데이터 검증과 문서화가 이루어집니다 .

FastAPI는 비동기 프로그래밍도 지원합니다. 엔드포인트 함수에서 `async`와 `await`를 사용하면 비동기 작업을 처리할 수 있습니다.

python

    @app.get("/async_items/{item_id}")
    async def read_async_item(item_id: int):
        # 비동기 작업 수행
        result = await some_async_operation(item_id)
        return {"item_id": item_id, "result": result}
    

마지막으로 애플리케이션을 실행하면 API 서버가 시작됩니다.

python

    if __name__ == "__main__":
        import uvicorn
        uvicorn.run(app, host="0.0.0.0", port=8000)
    

이렇게 FastAPI를 사용하면 Python의 타입 힌트 기능을 활용하여 API를 쉽고 빠르게 개발할 수 있습니다. 또한 비동기 프로그래밍 지원을 통해 높은 성능을 구현할 수 있습니다 .

FastAPI의 기본 기능 - 데이터 모델 정의
--------------------------

FastAPI에서는 Pydantic 라이브러리를 사용하여 데이터 모델을 정의합니다. Pydantic 모델을 통해 요청 본문의 필드와 중첩된 모델, 그리고 추가적인 데이터 모델을 정의할 수 있습니다.

예를 들어 Body - Fields 방식으로 다음과 같이 데이터 모델을 정의할 수 있습니다.

python

    from pydantic import BaseModel
    
    class Item(BaseModel):
        name: str
        description: str = None
        price: float
        tax: float = None
    

타입 힌트를 사용하여 필드와 타입을 선언하면, FastAPI에서 자동으로 데이터 검증과 직렬화/역직렬화를 수행합니다 . 이를 통해 개발자는 수동으로 검증 로직을 작성할 필요가 없어 생산성이 높아집니다.

데이터 모델은 자동 생성되는 대화형 문서에도 포함되므로, API의 요청/응답 데이터 형식을 쉽게 파악할 수 있습니다 . 따라서 FastAPI에서는 Pydantic을 사용하여 데이터 모델을 정의하고, 검증과 직렬화를 자동화함으로써 개발 생산성을 높일 수 있습니다.

FastAPI의 기본 기능 - 자동 API 문서화
---------------------------

FastAPI는 OpenAPI(Swagger) 명세를 기반으로 자동 대화형 API 문서를 생성합니다 . 이를 통해 개발자는 별도의 문서 작업 없이도 API의 엔드포인트, 매개변수, 응답 형식 등을 쉽게 확인할 수 있습니다.

FastAPI는 Swagger UI와 ReDoc 두 가지 시스템을 제공하여 API 문서를 렌더링합니다 . 두 시스템은 OpenAPI 스펙을 바탕으로 동작하며 기능은 비슷하지만 UI가 다릅니다. 개발자는 취향에 맞는 문서 시스템을 선택하면 됩니다.

Swagger UI는 `/docs` 경로에서 접근할 수 있고, ReDoc은 `/redoc`에서 접근할 수 있습니다. 두 시스템 모두 웹 브라우저에서 동작하며, API 엔드포인트와 매개변수를 확인하고 직접 테스트할 수 있습니다. 또한 문서에 설명을 추가할 수도 있습니다.

이처럼 FastAPI는 OpenAPI 스펙을 자동으로 생성하고, Swagger UI와 ReDoc를 통해 대화형 API 문서를 제공함으로써 개발자의 문서화 작업을 크게 줄여줍니다. 개발자는 코드에만 집중하면 되며, 프로덕션 레벨의 API 문서를 쉽게 만들 수 있습니다 .

FastAPI의 기본 기능 - 의존성 주입
-----------------------

FastAPI에서 의존성 주입(Dependency Injection)은 코드의 모듈화와 유연성을 높이는 중요한 개념입니다. 의존성 주입은 객체 간의 결합도를 낮춰 코드를 더 쉽게 유지보수하고 재사용할 수 있도록 돕습니다.

FastAPI에서는 `Depends` 데코레이터를 사용하여 의존성을 정의하고 주입할 수 있습니다. 예를 들어 데이터베이스 연결을 위한 의존성을 다음과 같이 만들 수 있습니다.

python

    from fastapi import Depends
    from db import get_db_connection
    
    def get_db():
        db = get_db_connection()
        try:
            yield db
        finally:
            db.close()
    
    @app.get("/users")
    def get_users(db=Depends(get_db)):
        # db 객체를 사용하여 사용자 데이터 조회
        ...
    

이렇게 `get_db` 함수를 의존성으로 정의하면, `get_users` 함수에서 데이터베이스 연결 객체를 자동으로 주입받게 됩니다. 이를 통해 데이터베이스 연결 로직을 분리하고 재사용할 수 있습니다 .

의존성 주입의 가장 큰 장점은 코드의 결합도를 낮추고 모듈화를 높일 수 있다는 점입니다. 각 기능별로 의존성을 분리하면 코드의 가독성과 유지보수성이 높아집니다. 또한 테스트 시에도 실제 객체 대신 가짜 객체를 주입하여 테스트하기 쉽습니다 .

FastAPI에서는 함수 매개변수뿐만 아니라 클래스 생성자, HTTP 요청 객체 등에도 의존성을 주입할 수 있습니다. 그리고 `Dependencies` 데코레이터를 사용하면 전역적으로 공유되는 의존성을 정의할 수 있습니다 .

이처럼 FastAPI의 의존성 주입 기능은 코드의 모듈화와 유연성을 높이고 테스트를 용이하게 합니다. 따라서 FastAPI로 애플리케이션을 개발할 때 의존성 주입 개념을 잘 활용하는 것이 중요합니다.

FastAPI의 기본 기능 - 비동기 지원
-----------------------

FastAPI는 ASGI(Asynchronous Server Gateway Interface) 서버를 사용하여 비동기 처리를 지원합니다. ASGI는 동기식 웹 서버와 달리 단일 스레드에서 동시에 여러 요청을 처리할 수 있습니다. 이를 통해 FastAPI는 높은 병렬성과 확장성을 제공할 수 있습니다.

FastAPI에서 비동기 함수는 `async` 키워드와 `await` 표현식을 사용하여 정의됩니다. 예를 들어 다음과 같이 비동기 함수를 작성할 수 있습니다:

python

    @app.get("/async_items/{item_id}")
    async def read_async_item(item_id: int):
        result = await some_async_operation(item_id)
        return {"item_id": item_id, "result": result}
    

위 코드에서 `read_async_item` 함수는 `async` 키워드로 비동기 함수임을 나타냅니다. 그리고 `some_async_operation` 함수의 결과를 기다리기 위해 `await` 표현식을 사용합니다. 이렇게 함으로써 FastAPI는 다른 요청을 처리하는 동안 현재 요청이 대기 상태에 머물 수 있게 됩니다 .

ASGI와 async/await 지원을 통해 FastAPI는 높은 동시성과 효율적인 리소스 사용을 제공하여 성능이 뛰어난 API를 구축할 수 있습니다 . 또한 비동기 프로그래밍 모델은 I/O 바운드 작업에서 특히 유용하며, 데이터베이스 연산, 파일 처리, 네트워크 요청 등의 작업에서 성능 향상을 가져올 수 있습니다 .

FastAPI의 장점
-----------

FastAPI는 Python 개발자들에게 다음과 같은 주요 장점을 제공합니다:

1.  개발 생산성 향상: FastAPI는 직관적인 API 설계와 자동 문서화 기능을 통해 기능 개발 속도를 200~300% 높일 수 있습니다 . 또한 Pydantic 라이브러리를 활용하여 데이터 검증과 직렬화를 자동화함으로써 개발 생산성을 크게 향상시킵니다 .
    
2.  높은 성능: FastAPI는 Starlette와 Pydantic를 기반으로 하여 NodeJS와 Go 수준의 매우 높은 성능을 제공합니다 . 또한 비동기 프로그래밍을 지원하여 높은 동시성과 효율적인 리소스 사용을 가능케 합니다 .
    
3.  데이터 검증 및 직렬화 자동화: FastAPI는 Pydantic 라이브러리를 통해 강력한 데이터 검증과 직렬화/역직렬화를 자동으로 수행합니다 . 이를 통해 개발자는 수동으로 검증 로직을 작성할 필요가 없어 생산성이 높아지고 버그도 줄어듭니다.
    
4.  OpenAPI 및 JSON 스키마 지원: FastAPI는 OpenAPI 명세와 JSON 스키마를 완벽히 지원하여, 자동 대화형 문서 생성과 클라이언트 코드 생성이 가능합니다 . 이를 통해 API 문서화 작업이 크게 줄어듭니다.
    
5.  통합 테스트 용이성: FastAPI는 테스트 클라이언트를 제공하여 API 통합 테스트를 용이하게 합니다 . 이를 통해 개발 및 테스트 주기가 단축되고 안정성이 높아집니다.
    

이처럼 FastAPI는 개발 생산성과 성능, 안정성을 모두 갖춘 현대적인 프레임워크로, Python 개발자들이 보다 효율적으로 API를 개발할 수 있도록 돕습니다.

FastAPI 활용 사례
-------------

FastAPI는 다양한 분야에서 활용될 수 있는 강력한 프레임워크입니다. 먼저 웹 애플리케이션의 백엔드 개발에 FastAPI를 사용할 수 있습니다. 직관적인 API 설계와 자동 문서화 기능을 통해 개발 생산성이 높아지며 , 우수한 성능과 비동기 프로그래밍 지원으로 확장성 있는 백엔드 시스템을 구축할 수 있습니다 .

또한 FastAPI는 마이크로서비스 아키텍처에 잘 어울립니다. 의존성 주입 기능을 통해 각 마이크로서비스의 모듈화가 용이해지며 , OpenAPI 스펙 지원으로 마이크로서비스 간 통신이 원활해집니다 . Netflix에서 위기 관리 프레임워크인 Dispatch를 FastAPI로 구축한 것이 대표적인 사례입니다.

데이터 API 구축에도 FastAPI가 적합합니다. Pydantic 라이브러리를 통한 자동 데이터 검증과 직렬화/역직렬화 기능으로 개발 생산성이 높아집니다 . 또한 OpenAPI 및 JSON 스키마를 지원하여 다양한 클라이언트에서 API를 쉽게 사용할 수 있습니다 .

머신러닝 모델 배포 시에도 FastAPI를 활용할 수 있습니다. Uber에서 Ludwig 프로젝트의 ML 모델 배포를 위해 FastAPI를 사용한 바 있습니다 . 빠른 성능과 비동기 지원으로 높은 처리량을 제공하며, 간단한 API 인터페이스로 모델 서빙이 용이해집니다.

마지막으로 IoT 및 센서 데이터 처리에 FastAPI가 활용될 수 있습니다. 비동기 프로그래밍 모델을 통해 대량의 센서 데이터를 효율적으로 처리할 수 있으며 , 경량화된 API 인터페이스로 IoT 디바이스와 원활하게 통신할 수 있습니다.

이처럼 FastAPI는 웹 애플리케이션 백엔드, 마이크로서비스, 데이터 API, 머신러닝 모델 배포, IoT 및 센서 데이터 처리 등 다양한 분야에서 활용도가 높습니다. 개발 생산성, 성능, 확장성, 모듈화 등 FastAPI의 장점을 살려 실제 다양한 프로젝트에 적용할 수 있습니다.

결론
--

FastAPI는 Python으로 개발된 모던하고 고성능의 웹 프레임워크로, 다음과 같은 주요 특징을 가지고 있습니다:

1.  매우 빠른 성능: NodeJS와 Go 수준의 뛰어난 성능을 제공합니다 .
2.  빠른 개발 속도: 기능 개발 속도를 약 200~300% 높일 수 있습니다 .
3.  적은 버그: 개발자 실수로 인한 버그를 약 40% 줄일 수 있습니다 .
4.  직관적이고 쉬운 사용법: 편집기 지원과 자동 완성 기능이 뛰어나고 배우기 쉽습니다 .
5.  간결한 코드: 코드 중복을 최소화하고 파라미터 선언으로 다양한 기능을 구현할 수 있습니다 .
6.  강력한 문서 생성: OpenAPI 명세를 자동으로 생성하여 대화형 API 문서를 제공합니다 .

이처럼 FastAPI는 개발 생산성, 성능, 안정성, 문서화 등 다양한 측면에서 장점을 제공하여 Python 개발자들이 보다 효율적으로 API를 개발할 수 있도록 돕습니다. 실제로 Microsoft, Uber, Netflix 등 유명 기업에서 FastAPI를 활용하고 있으며 , 개발자 커뮤니티에서도 인기가 높아지고 있습니다.

앞으로 FastAPI는 더욱 다양한 기능이 추가되고 성능이 향상될 것으로 기대되며, Python 웹 프레임워크 생태계에서 그 입지를 더욱 굳건히 할 것으로 전망됩니다. FastAPI 팀은 지속적인 업데이트와 개선을 통해 Python 개발자들에게 최신의 생산적이고 강력한 도구를 제공할 것입니다.

---
---

<iframe src="https://ads-partners.coupang.com/widgets.html?id=807239&template=carousel&trackingCode=AF3190673&subId=&width=680&height=140&tsource=" style="width:100%" height="140" frameborder="0" scrolling="no" referrerpolicy="unsafe-url" browsingtopics></iframe>
해당 링크를 통해 제품 구매가 이루어진 경우 쿠팡 파트너스 활동 일환으로 인해 일정 수수료가 블로거에게 제공되고 있습니다

