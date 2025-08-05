# 한국어 발음 평가 with Wav2Vec2

이 프로젝트는 Hugging Face의 `Wav2Vec2` 모델을 기반으로 한국어 음성에 대한 **발음 평가 기능**을 제공합니다.      
사용자가 녹음한 음성을 입력하면, Wav2Vec2 모델이 이를 텍스트로 변환하고 평가를 수행합니다.

---

## Wav2Vec2 사용 이유 및 장점

- **Self-supervised 학습 기반** : Wav2Vec2는 레이블이 없는 음성 데이터로 사전 학습되어 다양한 도메인에서도 높은 성능을 보임
- **사전 훈련 + 미세조정 구조** : 다양한 언어 및 태스크에 대해 fine-tuning이 가능해, 한국어 발음 인식에도 효과적
- **End-to-End 구조** : 별도 feature extraction 없이 원시 음성 waveform 입력만으로 처리 가능
- **Hugging Face Transformers 연동** : 쉽게 모델을 로드하고 사용할 수 있으며 커뮤니티 지원도 활발

---

## 주요 특징

- `Wav2Vec2ForCTC`를 사용하여 음성 인식을 수행
- 🇰🇷 한국어 발음을 평가하는 데 특화된 모델(`kresnik/wav2vec2-large-xlsr-korean`)
- STT 결과 기반으로 텍스트 분석 및 응용 가능
- 확장 가능: 발음 정확도, 발음 점수화, 피드백 시스템으로 확장 가능

---

## 실행 방법

### 1. 필수 라이브러리 설치

```bash
pip install -r requirements.txt
```

### 2. `main.py` 실행

```bash
python main.py
```

### 3. 예상 출력 예시

```json
{
    "score": 57,
    "transcribed": "그 치안했어요요",
    "reference": "아직 안 했어요."
}
```

---

## 파일 구조

```
.
├── main.py                # 실행 파일
├── stt_service.py         # Wav2Vec2 기반 STT 모듈
├── requirements.txt       # 의존성 패키지 목록
└── README.md              # 프로젝트 설명 문서
```

---

## Reference

- [Wav2Vec2 Paper](https://arxiv.org/abs/2006.11477)
- [kresnik/wav2vec2-large-xlsr-korean on Hugging Face](https://huggingface.co/kresnik/wav2vec2-large-xlsr-korean)
- [Hugging Face Transformers Documentation](https://huggingface.co/docs/transformers)
