# Hand Gesture Test - MediaPipe Index Finger Tracking

Google MediaPipe를 사용한 손가락 추적 및 랜드마크 시각화 웹 애플리케이션입니다.

## 🚀 기능

- **실시간 손 추적**: 웹캠을 통한 실시간 손 인식
- **Index Finger Tip 강조**: 검지 끝부분을 빨간색으로 특별 표시
- **랜드마크 시각화**: 모든 손가락 관절을 파란색 점으로 표시
- **연결선 표시**: 손가락과 손바닥의 연결선을 녹색으로 표시
- **실시간 좌표**: 검지 관련 관절들의 3D 좌표 실시간 표시
- **다중 손 인식**: 최대 2개의 손을 동시에 인식
- **반응형 디자인**: 모바일과 데스크톱 모두 지원

## 📋 사용 방법

1. **웹 브라우저에서 `index.html` 파일을 열기**
2. **카메라 권한 허용**: 브라우저에서 카메라 접근 권한을 허용
3. **카메라 시작**: "카메라 시작" 버튼 클릭
4. **손 보여주기**: 카메라 앞에 손을 보여주면 자동으로 인식
5. **결과 확인**: 
   - 빨간색 점: 검지 끝부분 (Index Finger Tip)
   - 파란색 점: 다른 손가락 관절들
   - 녹색 선: 손가락과 손바닥 연결선
   - 실시간 좌표 정보 업데이트

## 🎯 MediaPipe Hand Landmarks

MediaPipe는 각 손에 대해 21개의 랜드마크를 제공합니다:

### 검지 (Index Finger) 관련 랜드마크:
- **5번**: Index Finger MCP (Metacarpophalangeal joint)
- **6번**: Index Finger PIP (Proximal Interphalangeal joint)  
- **7번**: Index Finger DIP (Distal Interphalangeal joint)
- **8번**: Index Finger Tip (검지 끝부분) ⭐

### 다른 손가락들:
- **0-4번**: 엄지 (Thumb)
- **9-12번**: 중지 (Middle Finger)
- **13-16번**: 약지 (Ring Finger)
- **17-20번**: 소지 (Pinky)

## 🛠️ 기술 스택

- **MediaPipe**: Google의 머신러닝 프레임워크
- **HTML5**: 웹 페이지 구조
- **CSS3**: 스타일링 및 반응형 디자인
- **JavaScript**: MediaPipe API 연동 및 실시간 처리
- **WebRTC**: 웹캠 접근

## 📱 브라우저 지원

- Chrome (권장)
- Firefox
- Safari
- Edge

**주의**: HTTPS 환경에서만 웹캠 접근이 가능합니다.

## 🔧 설정 옵션

MediaPipe Hands 설정을 변경하려면 `initializeMediaPipe()` 함수에서 다음 옵션들을 조정할 수 있습니다:

```javascript
this.hands.setOptions({
    maxNumHands: 2,              // 최대 손 개수
    modelComplexity: 1,          // 모델 복잡도 (0-1)
    minDetectionConfidence: 0.5, // 최소 감지 신뢰도
    minTrackingConfidence: 0.5   // 최소 추적 신뢰도
});
```

## 📊 좌표 시스템

- **X축**: 0 (왼쪽) ~ 1 (오른쪽)
- **Y축**: 0 (위쪽) ~ 1 (아래쪽)  
- **Z축**: 손목에서 멀어질수록 양수값

## 🎨 커스터마이징

### 색상 변경:
- **Index Finger Tip**: `#ff0000` (빨간색)
- **다른 랜드마크**: `#0066ff` (파란색)
- **연결선**: `#00ff00` (녹색)

### 점 크기 조정:
```javascript
this.ctx.arc(x, y, 5, 0, 2 * Math.PI); // 현재 5px
```

## 🚨 문제 해결

### 카메라가 작동하지 않는 경우:
1. 브라우저에서 카메라 권한이 허용되었는지 확인
2. 다른 애플리케이션에서 카메라를 사용 중인지 확인
3. HTTPS 환경에서 실행하고 있는지 확인

### 손이 인식되지 않는 경우:
1. 충분한 조명 확보
2. 카메라와 손 사이의 적절한 거리 유지
3. 손이 카메라 화면에 완전히 들어오는지 확인

## 📄 라이선스

이 프로젝트는 교육 및 연구 목적으로 제작되었습니다.

## 🤝 기여

버그 리포트나 기능 제안은 언제든 환영합니다!

---

**개발자**: AI Assistant  
**프레임워크**: Google MediaPipe  
**버전**: 1.0.0
