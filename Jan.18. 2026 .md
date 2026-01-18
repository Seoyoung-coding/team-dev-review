.http 테스트로 검증해야 할 것은:

1. 인증된 사용자가 북마크를 추가할 수 있는가
2. 이미 북마크된 경우 예외가 터지는가
3. 북마크 해제가 정상 동작하는가
4. 인증 정보(@AuthenticationPrincipal)가 제대로 주입되는가
5. 서비스 로직이 DB에 반영되는가
```
@baseUrl = http://localhost:8080
@token = Bearer {{access_token}}

### 1️⃣ 북마크 추가 (처음 → 성공)
POST {{baseUrl}}/api/contents/1/bookmark
Authorization: {{token}}
이렇게?
```

### 임시 유저를 -> principaldetail로 바꾸기

### http 테스트 과정중 url과 controller가 맞지 않는 문제 계속 발생함
@PathVariable Long contentId
 이랑 @PathVariable("contentId") Long id 차이가 뭔데?

### 404 존나뜸
지금 404는 요청이 컨트롤러에 도달하지 못하는 상태

### public class FullContentResponse extends ContentResponse는 상속받기
엔티티 오류:Content.creator : Creator
Creator.user    : User





======== 해야 할것 ================================
    @DeleteMapping("/{contentId}")
    public ResponseEntity<Void> delete( //테스트해보기
            @AuthenticationPrincipal PrincipalDetails details,
            @PathVariable Long contentId


응답불친절 고치기
