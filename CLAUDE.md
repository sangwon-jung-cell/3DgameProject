# 프로젝트 개요
- 프로젝트명: allike
- 디아블로 스타일 3D ARPG (쿼터뷰/탑다운 시점)
- Unity 6000.6.1f1 / URP 17.6, Mac (Apple Silicon) 개발
- 1인 개발, 바이브코딩으로 진행 중

# 환경
- 입력: Input System (신형) 사용 — 레거시 `Input` 클래스 사용 금지
- 카메라: Cinemachine (추가 예정)
- 몬스터 이동: NavMesh (AI Navigation 패키지)
- 에디터 조작: Unity MCP 서버로 Claude가 에디터를 직접 조작

# 폴더 구조
- Assets/Scripts/ 아래에 모든 스크립트
- Assets/Scenes/ 아래에 씬 파일
- Assets/Editor/TemporaryGeneratedScripts/ — 임시 에디터 스크립트 전용
- 그 외 하위 구조는 기능 단위로 자유롭게 정리하되, 일관성 유지

# 코딩 컨벤션
- C# 네이밍은 Unity 표준 컨벤션 따르기 (PascalCase 클래스/메서드, camelCase 필드)
- 네임스페이스: `Allike.<기능>` (예: Allike.Player, Allike.Combat)
- MonoBehaviour는 얇게, 로직은 일반 C# 클래스/ScriptableObject로 분리
- 아이템/스킬/몬스터 스탯 등은 하드코딩 대신 ScriptableObject로 분리
- 매직 넘버 대신 상수나 설정값으로 관리

# 작업 규칙
- 프리팹/GameObject 생성·수정은 MCP 명령을 사용하고, .unity/.prefab YAML 파일을 직접 편집하지 않는다
- 임시로 만드는 에디터 스크립트는 Editor/TemporaryGeneratedScripts 폴더에 두고 작업 후 삭제한다
- .meta 파일은 Unity가 자동 생성하므로 직접 만들지 않는다
- 스크립트 작성 후 컴파일 에러는 MCP 콘솔 조회 또는 ~/Library/Logs/Unity/Editor.log로 확인

# 현재 진행 단계
- 버티컬 슬라이스 목표: 캐릭터 1명 + 스킬 1개 + 몬스터 1종 + 작은 맵 1개
- 지금 작업 중인 기능: 초기 설정 (프로젝트 구조 정리, MCP 연동 예정)

# 기타 참고사항
- 기능 하나씩 작게 요청하고 리뷰하는 방식 선호
