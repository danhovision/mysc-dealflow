# mysc-dealflow
MYSC 딜플로우 인텔리전스 에이전트

# 🔍 MYSC 딜플로우 인텔리전스 에이전트

> 투자 검토 요청 이메일을 자동으로 분석하고 Slack으로 브리핑하는 AI 에이전트

## 개요

MYSC 투자심사역의 딜 소싱 업무를 자동화하는 에이전트입니다.
Gmail로 수신되는 투자 검토 요청 이메일을 AI가 자동 분석하여
매일 Slack으로 브리핑을 발송합니다.

## 주요 기능

- 📥 Gmail 자동 모니터링 (읽지 않은 IR 이메일 수집)
- 🤖 Claude AI 기반 16개 항목 자동 추출
- 📁 A/C/H 폴더 자동 분류
  - 🟢 A폴더: 현재 최적화 (검증된 시장, 경쟁 우위)
  - 🔵 C폴더: 미래 최적화 (멱함수 잠재력, 비대칭 수익 가능)
  - 🟤 H폴더: 지역의 숨은 히어로 (지역 강소기업)
- 💬 Slack 팀 브리핑 자동 발송
- 🔗 7개 액셀러레이팅 프로그램 연계 추천
- 💚 소셜벤처 판별

## 분석 항목 (16개)

기업명, 대표자, 법인소재지, 창업연한, 투자단계, 희망투자금액,
산업분류, 재직자수, 매출, 특허, 벤처기업인증, 창업확인서,
TIPS, LIPS, 소셜벤처판별, 최근 뉴스

## 기술 스택

- Python 3.12
- Gmail API (Google Cloud)
- Anthropic Claude API
- Slack SDK
- Airtable API
- Schedule (자동 실행)

## 설치 방법

```bash
pip install google-auth google-auth-oauthlib google-api-python-client anthropic slack-sdk pyairtable schedule
```

## 실행 방법

```bash
# 1회 실행
python dealflow_agent.py --once

# 매일 09:00 자동 실행
python dealflow_agent.py
```

## 폴더 구조

dealflow/
├── dealflow_agent.py    # 메인 에이전트
├── credentials.json     # Google OAuth (비공개)
├── token.json          # Gmail 인증 토큰 (비공개)
└── processed_ids.json  # 처리된 이메일 추적

## 주의사항

⚠️ AI 1차 분류 결과입니다. 경계선 딜은 심사역 최종 판단이 필요합니다.

## 개발

MYSC 에이블(김정태) × Claude (Anthropic)
