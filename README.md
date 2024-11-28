# Docker контейнер

## Дасгал 1

nginx web сервер асааж welcome хуудсыг өөрийн веб хөтчөөс дуудан харуул.

## Дасгал 2

nginx web сервер асааж, /usr/share/nginx/html/-д өөрийн хавтсыг залгаж index.html-ийг өөрчилж харуул.

## Дасгал 3
Дараах 3 гарчгийг харуулах 3 ширхэг nginx контейнер асаа.
```
<h1> sysadmin 1</h1>
<h1> sysadmin 2</h1>
<h1> sysadmin 3</h1>
```

## Дасгал 4

Өмнөх дасгалын 3 web сервер дунд load balancer хийх 4 дэх nginx контейнер асаа. 4 дэх контейнер web хөтчөөсөө хандан хоорондоо round robin байдлаар солигдож байгааг хар.

```
http {
    upstream backend {
        server backend1.example.com;
        server backend2.example.com;
        server backend3.example.com;
    }

    server {
        location / {
            proxy_pass http://backend;
        }
    }
```

## Дасгал 5
Дараах 2 кодыг нэгийг нь alpine дээр, нөгөөг нь openjdk image дээр компайл хийж, компайл хийсэн файлуудаа, debian image-д хуулж 2ууланг нь дуудаж ажиллуулах эцсийн image-ийн build хийх Dockerfile бич.

```C++
#include <iostream>
using namespace std;
int main()
{
    cout << "hello world!\n";
    return 0;
}
```

```java
class Test
{
    public static void main(String []args)
    {
        System.out.println("My First Java Program.");
    }
};
```
