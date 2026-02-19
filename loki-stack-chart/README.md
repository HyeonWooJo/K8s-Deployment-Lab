# Loki Stack Helm Chart

이 Helm chart는 Grafana 공식 loki-stack chart를 subchart로 사용합니다.

## 구성 요소

- **Loki**: 로그 저장소
- **Promtail**: 로그 수집 에이전트
- **Grafana**: 로그 시각화 대시보드
- **Prometheus**: 메트릭 수집 (선택)

## 설치

ArgoCD를 통해 자동으로 배포되거나, 수동으로 설치할 수 있습니다:

```bash
# Helm dependency 업데이트 (로컬에서 테스트할 경우)
helm dependency update

# 설치
helm install loki-stack . -n logging --create-namespace
```

## 접속 정보

- **Grafana UI**: `http://localhost:8084`
- **기본 계정**: 
  - Username: `admin`
  - Password: `admin` (values.yaml에서 설정)

## 포트 매핑

kind-config.yaml에 따라:
- NodePort 30003 → Host Port 8084

## 네임스페이스

모든 리소스는 `logging` 네임스페이스에 배포됩니다.

