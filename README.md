# Shopping List App

간단한 쇼핑 리스트 웹 앱입니다. 별도의 서버나 빌드 도구 없이 브라우저에서 바로 실행됩니다.

## 기능
- 항목 추가 (add)
- 항목 체크 (check)
- 항목 삭제
- 완료 항목 일괄 지우기
- Supabase(Postgres) `shopping_items` 테이블을 이용한 데이터 저장 (기기 간에도 동기화됨)
- 다크 모드 지원 (`prefers-color-scheme`)

## 실행 방법
`index.html` 파일을 브라우저로 열기만 하면 됩니다.

## 데이터베이스
Supabase 프로젝트의 `public.shopping_items` 테이블에 데이터를 저장합니다.

| 컬럼 | 타입 | 설명 |
| --- | --- | --- |
| id | bigint (identity) | 기본 키 |
| text | text | 항목 이름 |
| checked | boolean | 완료 여부 (기본값 false) |
| created_at | timestamptz | 생성 시각 (기본값 now()) |

Row Level Security가 활성화되어 있으며, `anon` 역할에 대해 select/insert/update/delete를 모두 허용하는 정책이 설정되어 있습니다 (로그인 없이 누구나 사용할 수 있는 공개 리스트 앱이기 때문입니다).
