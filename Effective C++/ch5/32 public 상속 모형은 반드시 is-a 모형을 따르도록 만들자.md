클래스 사이 관게를 나타내는 모형
* is-a
* has-a 
* is-implemented-in-terms-of

C++에서 "is-a" 관계는 public 상속일 때만 해당


public 상속은 기본 클래스 객체가 가진 모든 것들이 파생 클래스 객체에도 그대로 적용된다고 단정하는 상속이다.
public 상속 모양을 사용하는 과정에서 코드가 컴파일되지만, 제대로 동작하지 않는 경우도 있을 것이다.
<br>

``` cpp
class Rectangle{
public:
    virtual void setHeight(int newHeight);
    virtual void setWidth(int newWidth);
    
    virtual int height() const;
    virtual int width() const;
};

void makeBigger(Rectangle& r)
{
    int oldHeight = r.height();
    r.setWidth(r.width() + 10);
    assert(r.height() == oldHeight);
}
```
직사각형을 상속받은 정사각형 클래스가 makeBigger 함수를 사용할 때
1. makeBigger 함수 호출전, 가로 세로 길이가 같아야 하는점
2. makeBigger 함수 호출 이후,가로 세로 길이가 같아야 한다는 점

직사각형의 성질 ( ex : 가로 길이가 세로 길이에 상관없이 바뀔 수 있는 성질) 은 정사각형에게 적용될 수 없다.
