 const 요청명세생성기 = (배송형태,요청사항,주문정보) =>{
        const 뭔가데이터오브젝트 = {
            method:배송형태,// post, get, delete 등 적기
            headers:요청사항,
            body:JSON.stringify(주문정보)//body data 문자열형태로 넣기
        }
        return 뭔가데이터오브젝트
    }
    const 가게 = "http://146.56.183.55:5050/user"
    const 요청명세 = 요청명세생성기("POST",{"Content-type" : "application/json"},userData)

    fetch(가게,요청명세).then((res)=>res.json()).then((json)=>console.log(json))

    //비동기로 진행되는 fetch는 web API가 코드를 순서대로 처리해주고 그 결과를 테스트큐에 넣어준 뒤 콜스택이 비면 결과가 나오게 됩니다.