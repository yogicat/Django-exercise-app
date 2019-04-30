# Django exercise

WIP 장고 연습 프로젝트

---

## Requirements

- python==3.6
- codecov==2.0.15
- Django==2.0
- django-extensions==2.1.6
- pytest==4.4.0
- requests==2.21.0
- urllib3==1.24.1


---

## 가상환경 세팅

`virtualenv`를 이용해 가상환경을 세팅한다.


### virtualenv 설치하기

`pip3 install virtualenv[==x.x.x]`

글로벌로 virtualenv를 설치한다. `==x.x.x` 특정 버전을 설치할땐 버전을 입력해준다.


### virtualenv로 환경세팅하기

`$ virtualenv -p python3.6 venv`

작업할 디렉토리에서 `venv`라는 디렉토리에 파이썬 가상환경을 세팅한다.


`$ source venv/bin/activate`- 가상환경을 활성화 한다.

`$ pip install -r requirements.txt` - 필요한 패키지를 설치한다.

`$ deactivate` - 가상환경 비활성화


## setting에 패키지적용하기

**settings.py**

```py
INSTALLED_APPS = [
    ...
    'django_extensions',
]
```

---

## Requirements 설명

**Django**

파이썬으로 만들어진 웹 프레임워크

**Django-extensions**

장고를 사용할때 유용한 기능들을 제공한다.


**codecov**

테스트 코드 커버리지를 측정해주는 라이브러리.(nodejs에서는 jest, istanbul와 유사함)
[링크](https://github.com/codecov/example-python)


**pytest**

테스트 코드 작성 라이브러리 (nodejs에서 jest, mocha와 유사함)

```py
# test_sample.py
def func(x):
    return x + 1

def test_answer():
    assert func(3) == 5
```

`$ pytest` # 테스트 실행

**requests**

Python에서 간편하게 HTTP요청(GET, POST, PUT, DELETE, ..)을 보낼 수 있게 하는 패키지.
urllib3를 가지고 만들어짐.

```py
import requests # pip으로 설치 후 import해서 사용

res = requests.get('https://api.github.com/events')
res.json() # json형태의 response는 .json()으로 dict로 변환한다.
```

**urllib3**

```py
import urllib3
http = urllib3.PoolManager()

res = http.request('GET', 'https://api.github.com/events')

```


**virtualenv**

다양한 버전의 프로젝트 개발을 위한 가상환경 세팅 도구.

