---
title: 마크다운이란 무엇인가?
author: alpa28980
date: Mon, 25 Nov 2024 05:02:33 GMT
categories: ["개발언어"]
tags: ["마크다운"]
comment: true
---
서론
--

마크다운(Markdown)은 웹에서 문서를 쉽고 빠르게 작성할 수 있도록 돕는 간단한 마크업 언어입니다. 존 그루버가 2004년에 만든 마크다운은 별도의 복잡한 태그 없이도 읽기 쉬운 문서를 작성할 수 있는 가벼운 문법을 제공합니다.

마크다운의 주요 특징은 다음과 같습니다:

1.  간단한 문법: 별도의 복잡한 태그 없이도 문서 작성이 가능합니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)).
2.  다양한 기능: 기본 문법 외에도 확장 문법을 통해 표, 코드 블록, 자동 링크 등 다양한 기능을 지원합니다.
3.  웹 친화적: 마크다운으로 작성된 문서는 HTML로 쉽게 변환되어 웹에 게시할 수 있습니다.
4.  오픈소스: 무료로 사용할 수 있는 오픈소스 프로젝트입니다.

마크다운은 이러한 특징 덕분에 개발자뿐만 아니라 일반 사용자들도 쉽게 문서를 작성하고 공유할 수 있습니다. 특히 GitHub, Reddit, 스택오버플로 등 많은 웹 서비스에서 마크다운을 공식적으로 지원하고 있어, 기술 문서나 블로그 포스트 등 웹 콘텐츠 작성에 널리 활용되고 있습니다. 마크다운의 간편성과 호환성은 협업 및 지식 공유를 용이하게 해주어 개발 커뮤니티에서 중요한 역할을 하고 있습니다.

헤딩 사용법
------

마크다운에서 헤딩은 문서 구조를 잡고 내용을 구분하는 데 사용됩니다. 헤딩에는 서로 다른 6개의 레벨이 있으며, 각 레벨은 #(해시 기호)의 개수로 나타냅니다. 예를 들면 다음과 같습니다:

가장 큰 헤딩 (H1)
============

두 번째로 큰 헤딩 (H2)
---------------

### 세 번째로 큰 헤딩 (H3)

#### 네 번째로 큰 헤딩 (H4)

##### 다섯 번째로 큰 헤딩 (H5)

###### 가장 작은 헤딩 (H6)

일반적으로 문서의 제목은 H1 레벨을, 큰 섹션의 제목은 H2 레벨을, 하위 섹션의 제목은 H3 레벨을 사용합니다. 그 이하의 레벨은 세부 내용을 구분할 때 사용할 수 있습니다.

헤딩 텍스트 뒤에는 공백이나 다른 마크다운 요소가 올 수 없습니다. 그렇지 않으면 헤딩으로 인식되지 않습니다. 예를 들어 다음과 같이 사용할 수 없습니다:

### 잘못된 사용

또한 각 #과 헤딩 텍스트 사이에는 공백이 있어야 합니다. 예를 들면:

#올바른 사용

헤딩은 문서의 목차와 구조를 만드는 데 매우 중요하므로 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)), 적절한 수준의 헤딩을 선택하는 것이 좋습니다.

단락 구분
-----

마크다운에서 단락을 구분하는 방법은 매우 간단합니다. 새로운 단락을 시작하려면 빈 줄을 삽입하기만 하면 됩니다. 예를 들어:

첫 번째 단락입니다. 이것은 첫 번째 단락의 내용입니다.

두 번째 단락입니다. 새로운 단락을 시작하기 위해 위의 빈 줄을 넣었습니다.

이렇게 빈 줄을 삽입하면 문서의 가독성과 구조화가 높아집니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 마크다운의 이러한 단순성은 누구나 쉽게 문서를 작성할 수 있게 해줍니다.

인용문 작성
------

마크다운에서 인용문을 작성하는 방법은 매우 간단합니다. 문장 앞에 >를 붙이기만 하면 해당 문장이 인용문으로 표시됩니다. 예를 들면 다음과 같습니다:

> 이것은 인용문 예시입니다.

인용문은 단락 단위로 구분되며, 연속된 인용문은 자동으로 하나의 인용문 블록으로 인식됩니다. 예를 들면:

> 이것은 첫 번째 인용문입니다.
> 
> 이것은 두 번째 인용문입니다.
> 
> 이렇게 여러 문장이 연속되면 하나의 인용문 블록으로 표시됩니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)).

인용문 안에 다른 마크다운 요소(헤딩, 목록, 강조 등)를 사용할 수도 있습니다. 이렇게 마크다운의 간단한 문법으로 인용문을 쉽게 작성할 수 있습니다.

굵게, 기울임, 취소선
------------

마크다운에서 텍스트에 다양한 스타일을 적용할 수 있습니다. 텍스트를 굵게 하거나 기울이거나 취소선을 넣는 등의 방법이 있습니다. 이렇게 텍스트 스타일을 다양화하면 문서의 가독성과 구조화가 높아집니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)).

먼저 텍스트를 굵게 하는 방법입니다. 단어나 구문 앞뒤에 두 개의 별표(\*\*) 또는 언더바(\_)를 붙이면 됩니다. 예를 들면:

**이렇게 별표로 감싸면 굵게 표시됩니다.** _이렇게 언더바로 감싸도 굵게 표시됩니다._

다음으로 텍스트를 기울이는 방법입니다. 단어나 구문 앞뒤에 한 개의 별표(\*) 또는 언더바(\_)를 붙이면 됩니다. 예를 들면:

_이렇게 별표로 감싸면 기울임꼴이 됩니다._ _이렇게 언더바로 감싸도 기울임꼴이 됩니다._

마지막으로 취소선을 넣는 방법입니다. 단어나 구문 앞뒤에 두 개의 물결 기호(~~)를 붙이면 됩니다. 예를 들면:

이렇게 물결 기호로 감싸면 취소선이 그어집니다.

이렇게 마크다운의 간단한 문법으로 텍스트에 다양한 스타일을 적용할 수 있습니다. 이를 활용하면 문서의 가독성과 구조화가 높아져 콘텐츠를 효과적으로 전달할 수 있습니다.

하이퍼링크 생성
--------

마크다운에서 하이퍼링크를 생성하는 방법은 매우 간단합니다. 링크를 걸고 싶은 텍스트를 대괄호(\[\])로 감싸고, 그 뒤에 실제 URL을 괄호(())로 감싸면 됩니다. 예를 들면 다음과 같습니다:

[구글 링크](https://www.google.com)

이렇게 하면 '구글 링크'라는 텍스트에 [https://www.google.com](https://www.google.com) 주소가 하이퍼링크로 연결됩니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)).

또한 참조 링크 스타일을 사용할 수도 있습니다. 이 방식은 링크와 URL을 분리하여 작성하므로 여러 곳에서 같은 링크를 사용할 때 유용합니다. 링크 텍스트를 대괄호로 감싸고, 링크 URL은 별도로 대괄호 안에 참조 이름을 작성하고 콜론(:) 뒤에 URL을 입력합니다. 예를 들면 다음과 같습니다:

[구글](https://www.google.com) [네이버](https://www.naver.com)

이렇게 하면 '구글'과 '네이버'라는 텍스트에 각각 구글과 네이버 사이트 링크가 연결됩니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)).

하이퍼링크는 마크다운 문서에서 다른 사이트나 페이지로 쉽게 연결할 수 있게 해주므로 문서의 유용성을 높여줍니다.

이미지 삽입
------

마크다운에서 이미지를 삽입하는 방법은 매우 간단합니다. 이미지를 보여주고 싶은 곳에 대괄호(\[\])로 이미지 설명을 감싸고, 그 뒤에 괄호(())로 이미지 URL을 감싸면 됩니다. 예를 들면 다음과 같습니다:

![예시 이미지](https://example.com/image.jpg)

이렇게 하면 "예시 이미지"라는 설명과 함께 [https://example.com/image.jpg](https://example.com/image.jpg) 이미지가 삽입됩니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 이미지 설명은 이미지를 볼 수 없는 환경에서 이미지 대신 보여지는 대체 텍스트로 사용됩니다.

이미지 URL은 웹 상에 있는 이미지 파일의 경로를 입력하면 됩니다. 또한 로컬 이미지 파일을 사용할 수도 있습니다. 이때는 상대 경로나 절대 경로를 입력하면 됩니다.

이렇게 이미지를 삽입하면 문서의 가독성과 이해도가 높아져 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)) 콘텐츠를 효과적으로 전달할 수 있습니다. 마크다운의 간단한 문법으로 쉽게 이미지를 추가할 수 있는 것이 큰 장점입니다.

순서 있는 목록과 순서 없는 목록
------------------

마크다운에서는 두 가지 유형의 목록을 만들 수 있습니다: 순서 있는 목록과 순서 없는 목록입니다.

순서 있는 목록은 번호가 매겨진 목록으로, 숫자와 마침표(.)로 항목을 나열합니다. 예를 들면 다음과 같습니다:

1.  첫 번째 항목
2.  두 번째 항목
3.  세 번째 항목

순서 있는 목록은 절차나 과정을 나열할 때 유용합니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)).

한편 순서 없는 목록은 번호 없이 기호로 항목을 나열합니다. 가장 일반적으로 사용되는 기호는 별표(\*)와 하이픈(-)입니다. 예를 들면:

*   사과
*   바나나
*   오렌지

*   축구
*   농구
*   야구

순서 없는 목록은 나열이나 요약할 때 유용합니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 목록 내에 또 다른 목록을 넣을 수도 있어 구조화가 가능합니다.

목록 안에 목록
--------

마크다운에서는 목록 안에 또 다른 목록을 넣어 구조화할 수 있습니다. 이를 통해 계층적인 정보를 쉽게 나타낼 수 있습니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)).

예를 들어 다음과 같이 순서 없는 목록 안에 순서 있는 목록을 넣을 수 있습니다:

*   과일
    1.  사과
    2.  바나나
    3.  오렌지
*   채소
    1.  당근
    2.  브로콜리
    3.  감자

또는 반대로 순서 있는 목록 안에 순서 없는 목록을 넣을 수도 있습니다:

1.  첫 번째 목록
    *   하위 항목 1
    *   하위 항목 2
2.  두 번째 목록
    *   하위 항목 1
    *   하위 항목 2

이렇게 중첩된 목록을 만들 때는 들여쓰기에 주의해야 합니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 상위 목록 항목과 하위 목록 항목 사이에는 최소 3칸 이상의 공백이나 탭이 있어야 합니다. 이렇게 하면 문서의 구조를 보기 좋게 구분할 수 있습니다.

체크박스 목록
-------

마크다운에서 체크박스 목록을 만드는 방법은 매우 간단합니다. 먼저 대시(-) 뒤에 공백을 두고 대괄호(\[\])를 작성합니다. 그리고 체크박스 안에 공백이나 x를 넣으면 됩니다. 예를 들면 다음과 같습니다:

*    체크되지 않은 항목
*    체크된 항목

이렇게 하면 체크박스 목록이 만들어집니다. 체크박스 앞에 내용을 추가하면 체크리스트를 만들 수 있습니다:

*    장 보기
*    청소하기
*    공부하기

체크박스 목록은 할 일 목록이나 체크리스트를 작성할 때 유용하게 사용할 수 있습니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 예를 들어 프로젝트의 진행 상황을 체크하거나 회의 안건을 체크하는 등 다양한 활용이 가능합니다. 또한 문서의 구조화에도 도움이 됩니다.

인라인 코드와 코드 블록
-------------

마크다운에서는 인라인 코드와 코드 블록의 두 가지 방식으로 코드를 표현할 수 있습니다.

인라인 코드는 작은 코드 조각을 문장 안에 넣는 방식입니다. 이를 위해서는 코드 조각을 백틱(\`\`)으로 감싸주면 됩니다. 예를 들어 `print("Hello, World!")`와 같이 사용할 수 있습니다. 인라인 코드는 주로 변수명, 함수명, 파일명 등을 나타낼 때 사용됩니다.

한편 코드 블록은 여러 줄의 코드를 별도의 블록으로 구분하여 표현하는 방식입니다. 코드 블록을 만들기 위해서는 코드 앞뒤에 세 개의 백틱(\`\`\`)을 넣거나, 혹은 각 줄 앞에 최소 4개 이상의 공백을 두면 됩니다. 예를 들어 다음과 같이 사용할 수 있습니다:

python

    # 파이썬 코드 예시
    def hello():
        print("Hello, World!")
    
    hello()
    

이처럼 코드 블록은 실제 프로그램 코드를 표시하거나 여러 줄의 코드 조각을 보여줄 때 유용하게 사용됩니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 마크다운의 이러한 코드 표현 기능을 활용하면 기술 문서나 튜토리얼 작성에 큰 도움이 됩니다.

코드 블록 언어 지정
-----------

마크다운에서 코드 블록에 프로그래밍 언어를 지정하면 구문 하이라이팅(syntax highlighting)이 적용되어 코드의 가독성이 높아집니다. 이를 위해서는 코드 블록의 첫 번째 백틱(\`\`\`) 뒤에 프로그래밍 언어 이름을 적으면 됩니다. 예를 들어 파이썬 코드라면 다음과 같이 작성할 수 있습니다:

python

    def hello():
        print("Hello, World!")
    
    hello()
    

여기서 `python`은 프로그래밍 언어 이름입니다. 이렇게 하면 파이썬 코드에 적합한 구문 하이라이팅이 적용됩니다.

다른 프로그래밍 언어도 마찬가지로 지정할 수 있습니다. 예를 들어 자바스크립트는 `javascript`, C++는 `cpp`, 자바는 `java`와 같이 작성하면 됩니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 언어 이름을 잘못 지정하면 구문 하이라이팅이 제대로 동작하지 않으므로 주의해야 합니다.

이렇게 마크다운의 코드 블록에 프로그래밍 언어를 지정하면 코드를 보다 명확하게 표현할 수 있어 문서의 가독성과 이해도가 높아집니다.

코드 블록 활용 예시
-----------

마크다운의 코드 블록 기능은 다양한 프로그래밍 언어의 코드 예제를 문서에 포함할 때 매우 유용하게 사용됩니다. 예를 들어 파이썬 코드라면 다음과 같이 작성할 수 있습니다:

python

    # 파이썬 함수 예시
    def factorial(n):
        if n == 0:
            return 1
        else:
            return n * factorial(n-1)
    
    print(factorial(5))  # 출력: 120
    

자바스크립트 코드의 경우:
```
javascript

    // 자바스크립트 함수 예시
    function greet(name) {
      console.log(`Hello, ${name}!`);
    }
    
    greet('John'); // 출력: Hello, John!
 ```   

또한 Java 코드도 다음과 같이 표현할 수 있습니다:

java
```
    // Java 클래스 예시
    public class HelloWorld {
        public static void main(String[] args) {
            System.out.println("Hello, World!");
        }
    }
```  

이처럼 마크다운의 코드 블록 기능을 활용하면 다양한 프로그래밍 언어의 코드 예제를 문서에 포함할 수 있습니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 또한 프로그래밍 언어를 지정하면 구문 하이라이팅이 적용되어 코드의 가독성도 높아집니다. 이는 기술 문서나 튜토리얼 작성에 큰 도움이 됩니다.

표 만들기
-----

마크다운에서 표를 만드는 방법은 다음과 같습니다. 먼저 표의 각 열을 파이프(`|`)로 구분하고, 두 번째 줄에서 열 제목을 작성한 후 아래 줄에서 각 열의 정렬 방식을 지정합니다. 정렬 방식은 콜론(`:`)의 위치에 따라 결정됩니다. 예를 들어:

제목1

제목2

제목3

내용1

내용2

내용3

내용4

내용5

내용6

이렇게 하면 제목1은 왼쪽 정렬, 제목2는 가운데 정렬, 제목3은 오른쪽 정렬된 표가 만들어집니다. 또한 표 내부에서도 마크다운의 다른 요소(링크, 강조, 코드 블록 등)를 사용할 수 있습니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 이렇게 표를 활용하면 데이터를 효과적으로 구조화하여 문서의 가독성을 높일 수 있습니다.

열 정렬
----

마크다운에서 표의 열 정렬 방식은 콜론(:)의 위치에 따라 결정됩니다. 콜론을 왼쪽에 두면 왼쪽 정렬, 오른쪽에 두면 오른쪽 정렬, 양쪽에 두면 가운데 정렬이 됩니다.

예를 들어 다음과 같이 작성하면 왼쪽 정렬 표가 만들어집니다:

제목1

제목2

제목3

내용1

내용2

내용3

내용4

내용5

내용6

가운데 정렬을 하려면 다음과 같이 콜론을 양쪽에 두면 됩니다:

제목1

제목2

제목3

내용1

내용2

내용3

내용4

내용5

내용6

마지막으로 오른쪽 정렬은 이렇게 작성합니다:

제목1

제목2

제목3

내용1

내용2

내용3

내용4

내용5

내용6

이처럼 마크다운에서는 간단한 문법으로 표의 열 정렬을 지정할 수 있습니다. 이를 통해 데이터를 보기 좋게 정렬하여 문서의 가독성을 높일 수 있습니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)).

표 내 텍스트 서식
----------

마크다운에서는 표 내부에서도 텍스트에 다양한 서식을 적용할 수 있습니다. 이를 통해 표의 가독성을 높이고 중요한 정보를 강조할 수 있습니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 표 내 텍스트 서식은 마크다운의 일반적인 텍스트 스타일 문법을 그대로 사용하면 됩니다.

먼저 텍스트를 굵게 표시하려면 별표(\*\*) 또는 언더바(\_)로 감싸면 됩니다. 예를 들어:

제목

설명

**강조**

이 텍스트는 굵게 표시됩니다.

_강조_

이 텍스트도 굵게 표시됩니다.

다음으로 텍스트를 기울임꼴로 표시하려면 별표(\*) 또는 언더바(\_)로 한 번만 감싸면 됩니다. 예:

제목

설명

_기울임_

이 텍스트는 기울임꼴입니다.

_기울임_

이 텍스트도 기울임꼴입니다.

취소선을 넣고 싶다면 물결 기호(~~)로 감싸면 됩니다:

제목

설명

취소선

이 텍스트에는 취소선이 그어집니다.

또한 코드 스타일을 적용하려면 백틱(\`\`)으로 감싸면 됩니다:

제목

설명

`코드`

이 텍스트는 코드 스타일입니다.

이렇게 마크다운의 기본 문법을 활용하면 표 내에서도 텍스트에 다양한 서식을 지정할 수 있습니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 이를 통해 표의 가독성과 구조화가 높아져 정보 전달력이 향상됩니다.

결론
--

마크다운은 간편한 문법과 다양한 기능으로 웹에서 문서를 쉽고 빠르게 작성할 수 있게 해주는 마크업 언어입니다. 마크다운의 핵심 장점은 바로 간단성입니다. 별도의 복잡한 태그 없이도 제목, 본문, 목록, 표, 코드 블록 등 다양한 요소를 문서에 포함할 수 있습니다 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)). 또한 웹 친화적이어서 마크다운 문서를 HTML로 손쉽게 변환할 수 있습니다. 이러한 간편성과 호환성 덕분에 마크다운은 기술 문서와 블로그 포스트 작성에 널리 활용되고 있습니다.

마크다운은 협업과 지식 공유에도 큰 역할을 하고 있습니다. GitHub, Reddit, 스택오버플로 등의 서비스에서 공식적으로 마크다운을 지원하고 있어, 개발자들이 문서를 쉽게 작성하고 공유할 수 있습니다. 마크다운의 확장 문법을 통해 표, 코드 블록, 수식 등 다양한 기능을 추가할 수 있어 \[[1](https://www.google.com)\]([https://www.markdownguide.org/](https://www.markdownguide.org/)) 개발 커뮤니티에서 중요한 역할을 하고 있습니다.

마크다운은 무료 오픈소스 프로젝트이며 지속적으로 발전하고 있습니다. 새로운 기능이 추가되고 지원 환경이 확대되면서 마크다운의 활용 범위는 더욱 넓어질 것으로 기대됩니다. 특히 최근 인공지능 기술의 발전으로 마크다운 문서를 자동으로 생성하거나 변환하는 것이 가능해지고 있어, 마크다운의 활용도는 더욱 높아질 전망입니다.
---
---

<iframe src="https://ads-partners.coupang.com/widgets.html?id=807239&template=carousel&trackingCode=AF3190673&subId=&width=680&height=140&tsource=" width="680" height="140" frameborder="0" scrolling="no" referrerpolicy="unsafe-url" browsingtopics></iframe>
해당 링크를 통해 제품 구매가 이루어진 경우 쿠팡 파트너스 활동 일환으로 인해 일정 수수료가 블로거에게 제공되고 있습니다

