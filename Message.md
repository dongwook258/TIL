* Spring Validation (JSR-380: Bean Validation 2.0) 기반의 국제화(i18n) 메시지 설정 방법
```
사용자의 언어 설정(Accept-Language)에 따라 @NotNull, @Size 등 제약 조건 위반 시
각 언어에 맞는 메시지로 응답되도록 구성하는 것입니다.
```
| 단계 | 설명                                                                  |
| -- | ------------------------------------------------------------------- |
| 1  | 검증 의존성 추가 (`spring-boot-starter-validation`)                        |
| 2  | `messages.properties`, `messages_ko.properties` 파일 생성               |
| 3  | `spring.messages.basename=messages` 설정                              |
| 4  | DTO 클래스에서 메시지 key로 참조 (`@NotNull(message = "{user.name.notnull}")`) |
| 5  | 컨트롤러에서 `@Valid`, `BindingResult`로 에러 메시지 추출                         |
| 6  | 클라이언트의 Locale에 따라 메시지가 자동 치환됨                                       |
| 7  | (선택) 커스텀 Locale 처리 로직 등록 가능                                         |
