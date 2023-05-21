# SpringBoot
### 스프링 부트 공부 기록
https://velog.io/@jjuyeoni/%EC%84%9C%EB%B8%94%EB%A6%BF
- hello 서블릿 호출
```
@WebServlet(name = "helloServlet", urlPatterns = "/hello")
public class HelloServlet extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {

        System.out.println("HelloServlet.service");
        System.out.println("req = " + req);
        System.out.println("resp = " + resp);
        
        String username = req.getParameter("username"); // 쿼리 파라미터 조회
        System.out.println("username = " + username);

        resp.setContentType("text/plain");
        resp.setCharacterEncoding("utf-8");
        resp.getWriter().write("hello " + username);

    }
}
```
- HttpServletRequest
  - 기본 사용법, Header 조회
  - HTTP 요청 메시지 바디 조회
    - GET -쿼리 파라미터
    - POST - HTML Form
    - HTTP API - MessageBody -> Postman 테스트
- HttpServletResponse
  - 기본 사용법, Header 조회
  - HTTP 응답 메시지 바디 조회
    - HTML 응답
    - HTTP API JSON 응답
