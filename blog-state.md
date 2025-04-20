# Don Bunny Park 블로그 상태 문서

## 블로그 메타데이터
```
{
  "name": "Don Bunny Park's Notes",
  "url": "https://moojittokki.github.io/donbunnypark.github.io/",
  "description": "AI와 IT를 배우고 활용하는 일상 블로그",
  "lastUpdated": "2025-04-20",
  "createdAt": "2025-04-15",
  "owner": "moojittokki",
  "motto": "AI도 잘 모르고, IT도 서툽니다. 그래도 써보면 뭔가 재미는 있어요. 그런 날것의 기록입니다."
}
```

## 파일 구조
```
donbunnypark.github.io/
├── README.md
├── index.html
├── styles.css
├── blog-state.md (이 문서)
└── posts/
    ├── first-post.html
    ├── claude-blogging.html
    └── disqus-comments.html
```

## 포스트 목록
```
[
  {
    "id": "disqus-comments",
    "title": "댓글 기능을 위한 작업들",
    "date": "2025-04-20",
    "path": "posts/disqus-comments.html",
    "description": "블로그에 Disqus 댓글 기능을 추가하는 과정과 reCAPTCHA 문제 해결, 그리고 AI의 문제 해결 능력에 대한 생각을 공유합니다.",
    "comments": true,
    "analytics": true
  },
  {
    "id": "claude-blogging",
    "title": "Claude를 이용하여 블로그하기",
    "date": "2025-04-15",
    "path": "posts/claude-blogging.html",
    "description": "Claude와 MCP를 활용하여 드디어 GitHub Pages 블로그를 만들게 된 경험과 AI 도구 활용에 대한 생각을 공유합니다.",
    "comments": true,
    "analytics": true
  },
  {
    "id": "first-post",
    "title": "블로그를 시작합니다",
    "date": "2025-04-15",
    "path": "posts/first-post.html",
    "description": "Don Bunny Park's Notes 블로그를 시작합니다. 앞으로 AI 도구들을 활용하면서 경험한 것들과 배운 것들을 기록할 예정입니다.",
    "comments": true,
    "analytics": true
  }
]
```

## 테마 및 디자인 정보
```
{
  "primaryFont": "Dongle, sans-serif",
  "fontWeights": ["300 (light)", "400 (regular)", "700 (bold)"],
  "fallbackFonts": "'Apple SD Gothic Neo', 'Nanum Gothic', 'Malgun Gothic', sans-serif",
  "primaryColor": "#2e73b8",
  "backgroundColor": "#f9f9f9",
  "textColor": "#333",
  "footerColor": "#333",
  "blockquoteStyle": "border-left: 4px solid #2e73b8",
  "responsive": true,
  "disqusLayout": {
    "marginLeft": "-2rem",
    "marginRight": "-2rem",
    "boxSizing": "border-box"
  }
}
```

## 관계 그래프 (Graph Database)
```
// 노드
Nodes = [
  { id: "blog", label: "블로그", type: "site" },
  { id: "index", label: "메인페이지", type: "page" },
  { id: "styles", label: "스타일시트", type: "asset" },
  { id: "readme", label: "README", type: "document" },
  { id: "posts_dir", label: "포스트 디렉토리", type: "directory" },
  { id: "post1", label: "블로그를 시작합니다", type: "post" },
  { id: "post2", label: "Claude를 이용하여 블로그하기", type: "post" },
  { id: "post3", label: "댓글 기능을 위한 작업들", type: "post" },
  { id: "disqus", label: "Disqus 댓글 시스템", type: "external_service" },
  { id: "google_analytics", label: "Google 애널리틱스", type: "external_service" }
]

// 엣지 (관계)
Edges = [
  { from: "blog", to: "index", relationship: "CONTAINS" },
  { from: "blog", to: "styles", relationship: "USES" },
  { from: "blog", to: "readme", relationship: "DESCRIBED_BY" },
  { from: "blog", to: "posts_dir", relationship: "CONTAINS" },
  { from: "posts_dir", to: "post1", relationship: "CONTAINS" },
  { from: "posts_dir", to: "post2", relationship: "CONTAINS" },
  { from: "posts_dir", to: "post3", relationship: "CONTAINS" },
  { from: "index", to: "styles", relationship: "IMPORTS" },
  { from: "post1", to: "styles", relationship: "IMPORTS" },
  { from: "post2", to: "styles", relationship: "IMPORTS" },
  { from: "post3", to: "styles", relationship: "IMPORTS" },
  { from: "index", to: "post1", relationship: "LINKS_TO" },
  { from: "index", to: "post2", relationship: "LINKS_TO" },
  { from: "index", to: "post3", relationship: "LINKS_TO" },
  { from: "post1", to: "disqus", relationship: "INTEGRATES" },
  { from: "post2", to: "disqus", relationship: "INTEGRATES" },
  { from: "post3", to: "disqus", relationship: "INTEGRATES" },
  { from: "blog", to: "google_analytics", relationship: "TRACKS_WITH" },
  { from: "index", to: "google_analytics", relationship: "TRACKED_BY" },
  { from: "post1", to: "google_analytics", relationship: "TRACKED_BY" },
  { from: "post2", to: "google_analytics", relationship: "TRACKED_BY" },
  { from: "post3", to: "google_analytics", relationship: "TRACKED_BY" }
]
```

## 컴포넌트 구조
```
{
  "header": {
    "title": "Don Bunny Park's Notes",
    "tagline": "AI와 IT를 배우고 활용하는 일상 블로그"
  },
  "mainPage": {
    "intro": {
      "title": "안녕하세요!",
      "quote": "AI도 잘 모르고, IT도 서툽니다.\n그래도 써보면 뭔가 재미는 있어요.\n그런 날것의 기록입니다."
    },
    "posts": {
      "title": "최근 글",
      "items": ["post3", "post2", "post1"]
    }
  },
  "postTemplate": {
    "header": "동일",
    "content": "포스트별 내용",
    "comments": "Disqus 댓글 시스템",
    "navigation": "홈으로 돌아가기 링크"
  },
  "footer": {
    "copyright": "© 2025 Don Bunny Park. All rights reserved."
  },
  "externalServices": {
    "disqus": {
      "shortname": "https-moojittokki-github-io-donbunnypark-github-io",
      "configPerPost": {
        "url": "[포스트의 전체 웹 주소]",
        "identifier": "[포스트 경로 또는 ID]",
        "title": "[포스트 제목]"
      },
      "layoutFixes": {
        "reCaptchaFix": "음수 마진을 통한 가로 공간 확보"
      }
    },
    "googleAnalytics": {
      "trackingID": "G-9MXXQ60B8Y",
      "implementation": "모든 페이지의 <head> 태그 안에 Google 애널리틱스 스크립트 추가"
    }
  }
}
```

## 마지막 변경 사항
- 생성일: 2025-04-15
- 마지막 업데이트: 2025-04-20
- 총 포스트 수: 3
- 모든 포스트에 Disqus 댓글 기능 추가 (2025-04-19)
- Disqus 댓글의 reCAPTCHA 레이아웃 문제 해결을 위한 CSS 수정 (2025-04-19)
- 모든 페이지에 Google 애널리틱스 추적 코드 추가 (2025-04-20)
- 새 포스트 추가: "댓글 기능을 위한 작업들" (2025-04-20)

## 앞으로 작업 시 참고사항
- 새 포스트 추가할 때 날짜 형식: "YYYY년 MM월 DD일"
- 모든 .html 파일에 스타일시트 링크 포함 필요
- 폰트 클래스 적용: dongle-light, dongle-regular, dongle-bold
- 모든 페이지에 헤더와 푸터 일관되게 유지
- 새 포스트 생성 시 다음 사항 추가 필요:
  1. Google 애널리틱스 추적 코드 (head 태그 내)
  2. Disqus 댓글 코드 (컨텐츠 영역 하단)
     - URL: 'https://moojittokki.github.io/donbunnypark.github.io/[포스트 경로]'
     - identifier: '[포스트 경로 또는 ID]'
     - title: '[포스트 제목]'