# MANDATORY CODEX SOURCE WORKFLOW｜Codex 강제 참조 제작 규칙

## 목적

앞으로 《棺中檀色》 관련 분진, 분할자료, 자리배치, 배경, 연기지도, 영상 프롬프트를 만들 때는 **무조건 Codex/GitHub 자료를 기준으로 먼저 확인**한다.

이 문서는 사용자의 최신 지시를 고정한다.

```text
무조건 Codex가 기준이다.
기억이나 감으로 프롬프트를 만들지 않는다.
Codex에 들어간 공식 분진, 캐릭터 기준, 배경 기준, 자가 체크 규칙을 먼저 확인한다.
```

---

## 1. 반드시 먼저 확인할 파일 순서

EP20 관련 출력 전에는 아래 파일을 먼저 기준으로 삼는다.

```text
1. FIXED_DIRECTOR_GENERATION_RULES.md
2. episode20_director_acting_image_guide.md
3. episode20_cut01_revised_official.md   ← CUT-01 전용 최신 수정본, CUT-01 작업 시 최우선
4. episode20_execution_prompt_pack.md    ← EP20 실행용 Prompt Pack, 이미지 키프레임/영상 Prompt/대사 시간/연속성 앵커 기준
5. episode20_character_reference_shen_bochuan.md
6. episode20_background_reference_old_house_gate.md
7. episode20_precision_self_check_rules.md
8. visual_split_expert_decision_tree.md
9. acting_split_reference_format_rules.md
10. acting_split_vs_shot_script_workflow.md
11. episode19_acting_split_timing_rules.md
```

기억, 이전 대화, 생성 이미지 결과보다 위 파일들이 우선이다.

특히 CUT-01은 `episode20_cut01_revised_official.md`가 기존 `episode20_director_acting_image_guide.md` 안의 CUT-01보다 우선한다.

영상 실행 프롬프트, 이미지 키프레임, 대사 시간, 연속성 앵커는 `episode20_execution_prompt_pack.md`를 우선 참조한다.

---

## 2. 출력 전 Codex 체크 의무

새 CUT 프롬프트를 만들기 전 반드시 아래를 점검한다.

```text
공식 CUT 번호:
공식 초수:
공식 분할 수:
공식 대사:
현재 배경:
등장 인물:
등장 금지 인물:
직전 CUT 마지막 상태:
다음 CUT 연결 상태:
도구/소품 연결:
카메라 기능:
이미지 키프레임:
영상 실행 Prompt:
대사 시간:
연속성 앵커:
```

이 항목 중 하나라도 Codex 기준과 맞지 않으면 바로 프롬프트를 출력하지 않는다.
먼저 수정 방향을 잡고 나서 출력한다.

---

## 3. 이미지 생성기와 Codex의 관계

이미지 생성기는 Codex/GitHub 파일을 직접 읽지 못한다.
따라서 작업자는 반드시 Codex 파일을 먼저 확인한 뒤, 이미지 생성기가 이해할 수 있도록 핵심만 프롬프트에 압축해서 넣어야 한다.

```text
Codex = 공식 기준.
프롬프트 = Codex 기준을 이미지 생성기에 전달하는 번역본.
이미지 결과 = 반드시 Codex 기준으로 다시 판정.
```

이미지 결과가 보기 좋아도 Codex 기준과 다르면 FAIL이다.

---

## 4. 결과 판정 방식

모든 생성 결과는 아래 기준으로 판정한다.

```text
PASS：Codex 공식 분진, 자리, 배경, 인물, 소품, 카메라, 대사 연결이 모두 맞음.
MINOR PASS：사용 가능하지만 한두 가지 보정문이 필요함.
FAIL：Codex 기준의 인물/배경/분할/소품/연결이 크게 틀어짐.
DISCARD：다시 쓰면 안 되는 폐기 결과.
```

사용자가 이미지를 올리면 먼저 아래처럼 판단한다.

```text
Codex 기준 판정：PASS / MINOR PASS / FAIL / DISCARD
틀린 이유：
다음 수정 방향：
```

---

## 5. CUT-01 특별 강제 규칙

CUT-01은 반드시 `episode20_cut01_revised_official.md`를 기준으로 한다.

```text
공식 CUT：CUT-01｜沈泊川入场｜12秒
공식 구조：0-4秒 静止死寂 / 4-12秒 沈泊川入场
분할 판단：공식상 2段
제작 안정화：필요 시 CUT-01-A, CUT-01-B 참고 이미지로 나누어 생성 가능
최종 영상：하나의 12초 CUT으로 합친다
```

CUT-01 배경은 최신 수정본을 따른다.

```text
格1（0-4秒）：完整昆仑旷野，无任何现实城市痕迹。
格2（4-12秒）：沈泊川骑摩托车入场时，沈泊川所在区域背景渐渐叠入城市轮廓。
城市元素包括：路灯、老旧楼房、柏油路面。
城市与昆仑旷野形成左右过渡边界。
昆仑还未消失，城市正在覆盖进来。
```

CUT-01 黑七规则：

```text
黑七必须是狐狸形态。
应依偎陆沉舟身侧或靠近陆沉舟低位。
不得人形站立。
不得狗化、狼化、怪物化。
```

---

## 6. 불안정 시 즉시 단순화

Codex 기준은 유지하되, 이미지 생성이 불안정하면 프롬프트를 더 복잡하게 하지 않는다.

```text
인물 수를 줄인다.
한 장 2분할이 실패하면 A/B 두 장으로 나눈다.
오토바이 같은 큰 물체는 주체 컷에서만 크게 보여준다.
기존 인물은 edge/background/silent 처리한다.
카메라는 고정한다.
금지문은 핵심 3-5개만 남긴다.
```

---

## 7. 절대 금지

```text
Codex 확인 없이 감으로 CUT 프롬프트 작성 금지.
생성 이미지가 그럴듯하다고 PASS 처리 금지.
스토리, 대사, 사건 순서 임의 변경 금지.
캐릭터 삼면도보다 임시 생성 이미지를 우선하는 것 금지.
배경 참고보다 생성 이미지의 잘못된 배경을 따라가는 것 금지.
FAIL 이미지를 다음 기준 이미지로 사용하는 것 금지.
```

---

## 8. 최종 작업 태도

```text
Codex 먼저 확인.
그다음 프롬프트 작성.
생성 결과는 Codex 기준으로 판정.
틀리면 문제 하나만 수정.
맞으면 더 이상 불필요하게 돌리지 않는다.
```
