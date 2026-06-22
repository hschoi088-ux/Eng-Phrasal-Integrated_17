
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>스피드 영어 퀴즈 (Week 13~17)</title>
    <style>
        body { font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, system-ui, Roboto, sans-serif; background-color: #f0f4f8; color: #333; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0; padding: 20px; box-sizing: border-box; }
        .container { background: white; padding: 30px; border-radius: 16px; box-shadow: 0 10px 30px rgba(0,0,0,0.08); max-width: 650px; width: 100%; }
        h1 { text-align: center; margin-bottom: 20px; color: #1e293b; font-size: 26px; }
        .week-tabs { display: flex; gap: 10px; margin-bottom: 25px; border-bottom: 2px solid #e2e8f0; padding-bottom: 10px; justify-content: center; flex-wrap: wrap; }
        .week-tab { padding: 10px 16px; border: none; background: none; font-size: 15px; font-weight: bold; color: #94a3b8; cursor: pointer; border-radius: 8px; transition: all 0.2s; }
        .week-tab.active { background-color: #e0f2fe; color: #0284c7; }
        .week-tab:hover:not(.active):not(:disabled) { background-color: #f1f5f9; }
        .week-tab:disabled { cursor: not-allowed; opacity: 0.5; }
        .category-section { margin-bottom: 25px; background: #f8fafc; padding: 20px; border-radius: 12px; border: 1px solid #e2e8f0; }
        .category-title { font-size: 18px; font-weight: bold; color: #334155; margin-top: 0; margin-bottom: 15px; display: flex; align-items: center; gap: 8px; }
        .flavor-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; }
        @media (max-width: 480px) { .flavor-grid { grid-template-columns: 1fr; } }
        .flavor-btn { background: white; border: 2px solid #cbd5e1; border-radius: 10px; padding: 15px; text-align: left; cursor: pointer; transition: all 0.2s ease; }
        .flavor-btn:hover { border-color: #3b82f6; box-shadow: 0 4px 12px rgba(59, 130, 246, 0.15); transform: translateY(-2px); }
        .flavor-title { font-size: 16px; font-weight: bold; display: block; margin-bottom: 6px; }
        .flavor-desc { font-size: 13px; color: #64748b; line-height: 1.4; word-break: keep-all; }
        .t-easy { color: #10b981; } .t-hard { color: #ef4444; }
        .hidden { display: none !important; }
        #quiz-area { display: flex; flex-direction: column; gap: 20px; }
        #question-counter { font-size: 15px; color: #64748b; font-weight: bold; text-align: center;}
        .question-box { font-size: 22px; font-weight: bold; word-break: keep-all; line-height: 1.5; background: #f8fafc; padding: 30px 20px; border-radius: 12px; border: 2px dashed #cbd5e1; cursor: pointer; transition: background 0.2s; text-align: center; }
        .question-box:hover { background: #e2e8f0; }
        .question-box::after { content: "(클릭하여 정답 확인)"; font-size: 13px; color: #94a3b8; display: block; margin-top: 10px; font-weight: normal; }
        .answer-box { background: #ecfdf5; padding: 25px 20px; border-radius: 12px; border: 1px solid #a7f3d0; text-align: left; }
        .en-text { font-size: 22px; color: #059669; font-weight: bold; margin-bottom: 15px; line-height: 1.4; word-break: keep-all;}
        .meta-info { font-size: 14px; color: #475569; margin-bottom: 5px; background: #fff; display: inline-block; padding: 4px 10px; border-radius: 20px; border: 1px solid #e2e8f0; }
        .meaning-info { font-size: 15px; color: #b45309; margin-bottom: 15px; background: #fef3c7; padding: 8px 12px; border-radius: 8px; font-weight: 500;}
        .controls { display: flex; justify-content: space-between; align-items: center; margin-top: 10px; flex-wrap: wrap; gap: 10px;}
        .left-controls { display: flex; gap: 10px; }
        .btn { padding: 10px 20px; border: none; border-radius: 8px; cursor: pointer; font-weight: bold; font-size: 15px; transition: 0.2s;}
        .btn-tts { background-color: #8b5cf6; color: white; display: flex; align-items: center; gap: 5px; }
        .btn-tts:hover { background-color: #7c3aed; }
        .btn-star { background-color: #e2e8f0; color: #475569; }
        .btn-star.active { background-color: #fef08a; color: #ca8a04; border: 1px solid #fde047; }
        .btn-next { background-color: #10b981; color: white; }
        .btn-next:hover { background-color: #059669; }
        .btn-finish { background-color: #3b82f6; color: white; width: 100%; padding: 15px; font-size: 16px; margin-top: 10px; }
        .btn-finish:hover { background-color: #2563eb; }
        .btn-home { background-color: #64748b; color: white; width: 100%; padding: 15px; font-size: 16px; margin-top: 20px;}
        .btn-home:hover { background-color: #475569; }
        #review-area { display: flex; flex-direction: column; gap: 15px; }
        .review-card { background: #fff; border: 1px solid #e2e8f0; border-radius: 10px; padding: 15px; box-shadow: 0 2px 5px rgba(0,0,0,0.05); text-align: left;}
        .review-ko { font-size: 16px; font-weight: bold; color: #334155; margin-bottom: 8px; }
        .review-en { font-size: 18px; font-weight: bold; color: #059669; margin-bottom: 8px; }
        .review-empty { text-align: center; padding: 40px 20px; font-size: 18px; color: #10b981; font-weight: bold; background: #ecfdf5; border-radius: 12px;}
    </style>
</head>
<body>

<div class="container">
    <h1 id="main-title">🚀 스피드 영어 퀴즈</h1>
    <div id="mode-selection">
        <div class="week-tabs">
            <button class="week-tab" onclick="setWeek(13, this)">Week 13</button>
            <button class="week-tab" onclick="setWeek(14, this)">Week 14</button>
            <button class="week-tab" onclick="setWeek(15, this)">Week 15</button>
            <button class="week-tab" onclick="setWeek(16, this)">Week 16</button>
            <button class="week-tab active" onclick="setWeek(17, this)">Week 17</button>
            <button class="week-tab" onclick="setWeek('all', this)">Week 13~17 누적</button>
        </div>
        <div class="category-section">
            <h3 class="category-title">🧩 구동사 (Phrasal Verbs)</h3>
            <div class="flavor-grid">
                <button class="flavor-btn" onclick="startQuiz('phrasal-easy')"><span class="flavor-title t-easy">🟢 순한맛</span><span class="flavor-desc">구동사 의미별로 짧고 쉬운 문장들이 선별해서 담겨있음</span></button>
                <button class="flavor-btn" onclick="startQuiz('phrasal-hard')"><span class="flavor-title t-hard">🔴 매운맛</span><span class="flavor-desc">전체 예문에서 선별됨</span></button>
            </div>
        </div>
        <div class="category-section">
            <h3 class="category-title">🗣️ 영어회화 (Conversation)</h3>
            <div class="flavor-grid">
                <button class="flavor-btn" onclick="startQuiz('conv-easy')"><span class="flavor-title t-easy">💬 순한맛</span><span class="flavor-desc">'대표문장'과 '교재1'만 담고 있음</span></button>
                <button class="flavor-btn" onclick="startQuiz('conv-hard')"><span class="flavor-title t-hard">🔥 매운맛</span><span class="flavor-desc">전체 예문에서 선별됨</span></button>
            </div>
        </div>
    </div>
    <div id="quiz-area" class="hidden">
        <div id="question-counter">문제 1 / 7</div>
        <div class="question-box" id="ko-box" onclick="showAnswer()"><span id="ko-text">한국어 문장</span></div>
        <div class="answer-box hidden" id="answer-section">
            <div class="meta-info" id="source-info">출처</div>
            <div class="en-text" id="en-text">English Answer</div>
            <div class="meaning-info hidden" id="meaning-info">의미</div>
            <div class="controls">
                <div class="left-controls"><button class="btn btn-tts" onclick="playTTS()">🔊 듣기</button><button class="btn btn-star" id="btn-star" onclick="toggleStar()">⭐ 어려워요</button></div>
                <button class="btn btn-next" id="btn-next" onclick="nextQuestion()">다음 문제 ➡</button>
            </div>
        </div>
        <button class="btn btn-finish hidden" id="btn-finish" onclick="showReview()">결과 보기 (오답 노트) 📝</button>
    </div>
    <div id="review-area" class="hidden">
        <h2 style="text-align: center; color: #1e293b; margin-top:0;">⭐ 나의 오답 노트</h2>
        <p style="text-align: center; color: #64748b; font-size: 14px; margin-top:-10px;">어려웠던 문장들을 다시 확인해 보세요!</p>
        <div id="review-list"></div>
        <button class="btn btn-home" onclick="resetToHome()">🏠 처음으로 돌아가기</button>
    </div>
</div>

<script>
    let currentWeekFilter = 17;
    function setWeek(week, btn) {
        if (week === 'all') currentWeekFilter = 'all';
        else currentWeekFilter = parseInt(week);
        document.querySelectorAll('.week-tab').forEach(el => el.classList.remove('active'));
        btn.classList.add('active');
    }

    // 📌 구동사 전체 (Week 13~17) 의미 매핑
    const meanings = {
        // Week 13
        "mess around_1": "mess around: (고장 날 위험이 있는 사물을) 자꾸 만지작거리다",
        "mess around_2": "mess around: (해야 할 일을 안 하고) 빈둥거리며 시간을 보내다",
        "mess around_3": "mess around: (진지하지 않게 가벼운 태도로) 장난치다",
        "mess around_4": "mess around: (이성과 진지하지 않은 관계를 맺으며) 시간을 허비하다",
        "mess up_1": "mess up: (실수를 저질러 상황을) 망치다",
        "mess up_2": "mess up: (깔끔했던 것을 지저분하게) 엉망으로 만들다",
        "mess with_1": "mess with: (커피 등이 수면 등에) 안 좋은 영향을 미치다, 방해하다",
        "mess with_2": "mess with: (트러블을 피하기 위해 특정인과) 더는 엮이지 않다",
        "mess with_3": "mess with: (상대를 골탕 먹이려고 장난삼아) 놀리다",
        "mess with_4": "mess with: (남의 물건이나 설정을 부주의하게 만져서) 망가뜨리다",
        "mess with_5": "mess with: (화난 사람을) 괜히 자극하다, 건드리다",
        "miss out_1": "miss out: (남들은 다 누리는) 좋은 기회나 즐거움을 놓치다",
        "move on_1": "move on: (한 장소에서 머물다가 다른 장소로) 이동하다",
        "move on_2": "move on: (하던 일을 마치고 다음 단계/질문으로) 넘어가다",
        "move on_3": "move on: (이별 후 상처를 잊고) 새로운 출발을 하다",
        "move on_4": "move on: (과거의 팬이나 지지자가) 이미 마음이 떠나버리다",
        
        // Week 14
        "pass for_1": "pass for: (실제와 달라도 겉보기에) ~으로 통하다, 믿어지다",
        "pass for_2": "pass for: (의도적으로) ~인 척하다, 위장하다",
        "pass up_1": "pass up: (아깝지만 불가피한 상황 때문에) 기회를 거절하다, 포기하다",
        "pick up_1": "pick up: (바닥에 있는 것을 손으로) 집어 올리다",
        "pick up_2": "pick up: (차에 태우기 위해 특정 장소로) 마중 나가다, 태우다",
        "pick up_3": "pick up: (집에 오는 길에 가벼운 물건을) 사 오다",
        "pick up_4": "pick up: (타인의 말투나 습관 등을 무의식적으로) 닮게 되다, 배우다",
        "pick up_5": "pick up: (중단되었던 대화나 일을) 멈춘 지점부터 다시 시작하다",
        "pick up on_1": "pick up on: (남들은 모르는 미묘한 변화나 뉘앙스를) 알아차리다",
        "pull off_1": "pull off: (몸에 꽉 끼는 옷 등을) 힘들게 벗다, 떼어내다",
        "pull off_2": "pull off: (소화하기 힘든 패션 등을) 멋지게 소화해 내다",
        "pull off_3": "pull off: (모두가 불가능하다고 여긴 일을) 성공시키다, 해내다",

        // Week 15
        "put away_1": "put away: (사용한 물건을 원래 있던) 제자리에 두다",
        "put away_2": "put away: (장래를 위해 돈을 꾸준히) 저축하다",
        "put away_3": "put away: (엄청난 양의 음식을 단숨에) 해치우다, 먹어 치우다",
        "put down_1": "put down: (손에 들고 있던 것을 바닥에) 내려놓다",
        "put down_2": "put down: (잊지 않기 위해 종이에) 적다, 기재하다",
        "put down_3": "put down: (예약이나 렌트를 위해 보증금을) 예치하다, 맡기다",
        "put down_4": "put down: (남들 앞에서 상대를) 무시하거나 깎아내리는 말을 하다",
        "put off_1": "put off: (하기 싫거나 준비가 안 되어 일정을) 나중으로 미루다",
        "put off_2": "put off: (안 좋은 냄새나 태도 등이 상대를) 정떨어지게 만들다",
        "put on_1": "put on: (옷/안경 등을 몸에 걸치는) '동작'을 하다",
        "have on_1": "have on: (옷/안경 등을 이미 몸에 걸치고 있는) '상태'이다",
        "try on_1": "try on: (사이즈나 어울림을 보려고) 시험 삼아 입어 보다",
        "put together_1": "put together: (부품을 모아 가구 등을) 직접 조립하다",
        "put together_2": "put together: (사람이나 아이디어를 모아 팀/계획을) 구성하다",
        "put together_3": "put together: (수치를 모두 합산하여) 다 합치다",

        // Week 16
        "put up_1": "put up: (벽이나 높은 곳에 포스터 등을) 올리다, 붙이다",
        "put up_2": "put up: (울타리나 건물 등을 토대부터) 세우다, 짓다",
        "put up_3": "put up: (SNS 등에 사진이나 게시글을) 올리다",
        "put up_4": "put up: (여행 온 사람 등을 집에서 몇 밤) 재워 주다",
        "put up with_1": "put up with: (불편한 출퇴근 등 어쩔 수 없는 상황을) 참고 견디다",
        "put up with_2": "put up with: (성격이 힘든 특정 사람의 태도를) 인내심 있게 참아주다",
        "run into_1": "run into: (실수로 사물 등에) 물리적으로 꽝 부딪히다",
        "run into_2": "run into: (길에서 아는 사람을) 우연히 마주치다",
        "run into_3": "run into: (예상치 못한 난관이나 문제에) 맞닥뜨리다",
        "settle for_1": "settle for: (최선은 아니지만 아쉬운 대로) 차선책에 만족하다",
        "show off_1": "show off: (남의 관심을 끌려고 장점을) 과시하다, 으스대다",
        "brag about_1": "brag about: (말로 자기 자랑을 늘어놓으며) 뽐내다",

        // Week 17 추가
        "slack off_1": "slack off: (공부나 일을 안 하고) 나태하게 게으름을 피우다",
        "slack off_2": "slack off: (매출이나 기세 등이 이전보다) 약화되다, 주춤하다",
        "sort out_1": "sort out: (재활용품 등을 기준에 맞게) 알맞게 분류하다",
        "sort out_2": "sort out: (어지럽게 널브러진 물건들을) 정리하다",
        "sort out_3": "sort out: (복잡하게 얽힌 문제나 오해를) 해결하다, 해소하다",
        "sort out_4": "sort out: (여행 경로 등 세부적인 계획을) 짜다",
        "stick around_1": "stick around: (가야 할 시간임에도 그 자리에) 좀 더 머물다",
        "stick around_2": "stick around: (냄새 등이 환기되지 않고 공간에) 남다",
        "stick around_3": "stick around: (새로운 기술 등이 반짝 유행에 그치지 않고) 계속 지속되다",
        "stick it out_1": "stick it out: (힘들어도 포기하지 않고) 끝까지 버티다",
        "tough it out_1": "tough it out: (육체적/정신적 고통을 묵묵히) 참고 견뎌내다",
        "stop by_1": "stop by: (목적지로 가는 길에 아주 잠깐) 들르다",
        "come by_1": "come by: (방문을 목적으로 상대적으로 시간을 내어) 들르다",
        "drop by_1": "drop by: (정중하게 혹은 예고 없이 쑥) 방문하다, 들르다",
        "swing by_1": "swing by: (지나가는 길에 가볍고 빠르게) 휙 들르다"
    };

    // 1. 구동사 순한맛 (Week 13~17)
    const phrasalEasy = [
        // Week 13
        { week: 13, ko: "휴대폰 그만 만지작거려.", en: "Stop messing around with your phone.", source: "Day 061 순한맛", meaning: meanings["mess around_1"] },
        { week: 13, ko: "비디오 게임을 하면서 계속 빈둥거리네요.", en: "My son keeps messing around with video games when he should be studying for his exams.", source: "Day 061 순한맛", meaning: meanings["mess around_2"] },
        { week: 13, ko: "그냥 장난친 거라고.", en: "I was just trying to mess around.", source: "Day 061 순한맛", meaning: meanings["mess around_3"] },
        { week: 13, ko: "이제 여러 이성을 만나는 것도 지겹습니다.", en: "I am tired of messing around.", source: "Day 061 순한맛", meaning: meanings["mess around_4"] },
        { week: 13, ko: "공연 때 대사 몇 개를 잘못 말했지 뭐야.", en: "During the play, I messed up several of my lines.", source: "Day 062 순한맛", meaning: meanings["mess up_1"] },
        { week: 13, ko: "그가 취소하는 바람에 제 스케줄 전체가 꼬여 버렸습니다.", en: "His cancellation has messed up my whole schedule.", source: "Day 062 순한맛", meaning: meanings["mess up_2"] },
        { week: 13, ko: "늦은 시간에 커피 마시지 말아야겠어; 수면에 방해가 돼.", en: "I have to stop drinking coffee late; it messes with my sleep.", source: "Day 063 순한맛", meaning: meanings["mess with_1"] },
        { week: 13, ko: "더 이상 Brandon이랑은 엮이기 싫어.", en: "I don’t mess with Brandon anymore.", source: "Day 063 순한맛", meaning: meanings["mess with_2"] },
        { week: 13, ko: "그냥 한 말이야.", en: "I was just messing with you.", source: "Day 063 순한맛", meaning: meanings["mess with_3"] },
        { week: 13, ko: "이봐, 내 카메라 설정 건드린 거야?", en: "Hey, did you mess with the settings on my camera?", source: "Day 063 순한맛", meaning: meanings["mess with_4"] },
        { week: 13, ko: "주방에 있는 분은 건드리면 안 된다는 걸 알게 되었어요.", en: "I learned the hard way not to mess with kitchen staff.", source: "Day 063 순한맛", meaning: meanings["mess with_5"] },
        { week: 13, ko: "이건 너무 중요한 기회야! 절대로 그냥 보내지 않을 거야.", en: "This is a huge chance! I’m not going to miss out on it.", source: "Day 064 순한맛", meaning: meanings["miss out_1"] },
        { week: 13, ko: "저녁 먹고, 조용한 와인바로 이동해서 몇 시간 동안 이야기를 나누었어.", en: "We had dinner and moved on to a quiet wine bar where we talked for hours.", source: "Day 065 순한맛", meaning: meanings["move on_1"] },
        { week: 13, ko: "답을 모르겠으면, 다음 문제로 넘어갔다가 다시 풀어 봐.", en: "Move on and try again when you’ve finished the easier ones.", source: "Day 065 순한맛", meaning: meanings["move on_2"] },
        { week: 13, ko: "전 남자 친구를 굉장히 빨리 잊는 것 같아.", en: "I guess she moves on really fast.", source: "Day 065 순한맛", meaning: meanings["move on_3"] },
        { week: 13, ko: "스캔들 이후에 그의 팬 중 많은 이들의 마음이 이미 떠난 상태다.", en: "Following the scandal, many of his fans have already moved on.", source: "Day 065 순한맛", meaning: meanings["move on_4"] },
        
        // Week 14
        { week: 14, ko: "재미 교포라고 해도 믿을 것이다.", en: "He can pass for a Korean-American.", source: "Day 066 순한맛", meaning: meanings["pass for_1"] },
        { week: 14, ko: "그는 정상적인 은행원인 척 거짓 삶을 살았다.", en: "He was living his life, passing for a normal banker and husband.", source: "Day 066 순한맛", meaning: meanings["pass for_2"] },
        { week: 14, ko: "세일하는 걸 그냥 지나칠 수가 없었다.", en: "I couldn’t pass up (on) the sale.", source: "Day 067 순한맛", meaning: meanings["pass up_1"] },
        { week: 14, ko: "원두는 쏟으면 줍기가 번거롭다.", en: "Coffee beans are a hassle to pick up if you spill them.", source: "Day 068 순한맛", meaning: meanings["pick up_1"] },
        { week: 14, ko: "내가 회사로 태우러 갈게.", en: "I will pick you up from work.", source: "Day 068 순한맛", meaning: meanings["pick up_2"] },
        { week: 14, ko: "집에 가는 길에 저녁거리 좀 사 갈게.", en: "I’ll pick up something for dinner on my way home.", source: "Day 068 순한맛", meaning: meanings["pick up_3"] },
        { week: 14, ko: "그분들 때문에 그렇게 표현하게 된 것 같아요.", en: "I think I picked up that expression from the Canadians in my office.", source: "Day 068 순한맛", meaning: meanings["pick up_4"] },
        { week: 14, ko: "어제 마친 부분부터 다시 이야기할까요?", en: "Let’s pick up where we left off yesterday.", source: "Day 068 순한맛", meaning: meanings["pick up_5"] },
        { week: 14, ko: "민지는 생각보다 빠르게 언어의 뉘앙스를 알아차리더군요.", en: "Minji picked up on the nuances of the language faster than expected.", source: "Day 069 순한맛", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "청바지 벗는 게 쉽지 않다.", en: "I have a hard time pulling my jeans off after a big dinner.", source: "Day 070 순한맛", meaning: meanings["pull off_1"] },
        { week: 14, ko: "나는 소화하기 어렵다.", en: "I can’t pull it off.", source: "Day 070 순한맛", meaning: meanings["pull off_2"] },
        { week: 14, ko: "할 수 있겠어?", en: "Do you think you can pull it off?", source: "Day 070 순한맛", meaning: meanings["pull off_3"] },

        // Week 15
        { week: 15, ko: "반드시 운동기구를 제자리에 두기 바랍니다.", en: "Please be sure to put away weights after you use them.", source: "Day 071 순한맛", meaning: meanings["put away_1"] },
        { week: 15, ko: "저축할 돈이 거의 남지 않아요.", en: "I don’t have any money left to put away after paying all my bills.", source: "Day 071 순한맛", meaning: meanings["put away_2"] },
        { week: 15, ko: "혼자서 삼겹살 3인분을 해치우지.", en: "This mukbang YouTuber can put away three servings of pork belly by herself.", source: "Day 071 순한맛", meaning: meanings["put away_3"] },
        { week: 15, ko: "휴대폰 내려놓고 저녁 먹어야지!", en: "Put down your phone and eat your dinner!", source: "Day 072 순한맛", meaning: meanings["put down_1"] },
        { week: 15, ko: "제 생각을 적으려고 합니다.", en: "I try to put down my thoughts on paper when I have too many things to do.", source: "Day 072 순한맛", meaning: meanings["put down_2"] },
        { week: 15, ko: "보증금으로 30만원을 예치해야 합니다.", en: "We require that our customers put down a 300,000 won security deposit to rent a car.", source: "Day 072 순한맛", meaning: meanings["put down_3"] },
        { week: 15, ko: "꼭 그렇게 나를 깎아내려야 했어?", en: "Why did you have to put me down in front of everybody like that?", source: "Day 072 순한맛", meaning: meanings["put down_4"] },
        { week: 15, ko: "몇 달째 미루고 있던 복잡한 세금 서류 알지? 드디어 처리했어.", en: "You know that complicated tax paperwork I was putting off for months? I finally got around to it.", source: "Day 073 순한맛", meaning: meanings["put off_1"] },
        { week: 15, ko: "담배 냄새가 정말 정이 떨어진다.", en: "The smell of tobacco really puts me off.", source: "Day 073 순한맛", meaning: meanings["put off_2"] },
        { week: 15, ko: "그냥 모자 쓰고 가자.", en: "Just put on a hat and let’s go.", source: "Day 074 순한맛", meaning: meanings["put on_1"] },
        { week: 15, ko: "양말을 안 신었네?", en: "You don’t have any socks on?", source: "Day 074 순한맛", meaning: meanings["have on_1"] },
        { week: 15, ko: "결정하기 전에 입어 보려고요.", en: "I want to try this on before I decide.", source: "Day 074 순한맛", meaning: meanings["try on_1"] },
        { week: 15, ko: "직접 조립할 수 없어요.", en: "I can’t put together anything that requires a drill.", source: "Day 075 순한맛", meaning: meanings["put together_1"] },
        { week: 15, ko: "우리 머리를 맞대어서 올여름 재미있는 여행 계획을 짜 보자.", en: "Let’s put our heads together and plan a fun trip this summer.", source: "Day 075 순한맛", meaning: meanings["put together_2"] },
        { week: 15, ko: "이번 신규 스마트폰 모델의 첫 주 판매치가 이전 모델을 다 합친 것보다 더 많았다.", en: "The sales of this new smartphone model in its first week exceeded those of all previous models put together.", source: "Day 075 순한맛", meaning: meanings["put together_3"] },

        // Week 16
        { week: 16, ko: "포스터 붙일 멋진 곳을 방금 찾았어!", en: "I just found a great place to put up our posters!", source: "Day 076 순한맛", meaning: meanings["put up_1"] },
        { week: 16, ko: "정원에 울타리를 칠까 해요.", en: "We were thinking of putting up a fence around our garden to keep out the neighbors’ dogs.", source: "Day 076 순한맛", meaning: meanings["put up_2"] },
        { week: 16, ko: "인스타에 올리자.", en: "Let’s put up these pictures of the decor on Instagram before we head out.", source: "Day 076 순한맛", meaning: meanings["put up_3"] },
        { week: 16, ko: "Jeff가 몇 주간 재워 줬답니다.", en: "Jeff put me up for a few weeks.", source: "Day 076 순한맛", meaning: meanings["put up_4"] },
        { week: 16, ko: "출퇴근을 언제까지 견딜 수 있을지 모르겠어요.", en: "I don’t know how long I can put up with this two-hour commute every day.", source: "Day 077 순한맛", meaning: meanings["put up with_1"] },
        { week: 16, ko: "네 아내가 너를 어떻게 참지?", en: "How does your wife put up with you?", source: "Day 077 순한맛", meaning: meanings["put up with_2"] },
        { week: 16, ko: "결국 회전문에 부딪히고 말았어요.", en: "I was staring at my phone and ended up running into the revolving door.", source: "Day 078 순한맛", meaning: meanings["run into_1"] },
        { week: 16, ko: "여기서 보다니 반갑다!", en: "Nice running into you!", source: "Day 078 순한맛", meaning: meanings["run into_2"] },
        { week: 16, ko: "착륙 직전에 난기류를 만났습니다.", en: "We ran into some turbulence just before landing.", source: "Day 078 순한맛", meaning: meanings["run into_3"] },
        { week: 16, ko: "그냥 작년 모델에 만족해야 했어요.", en: "I just settled for last year’s model, instead.", source: "Day 079 순한맛", meaning: meanings["settle for_1"] },
        { week: 16, ko: "여자애들에게 잘 보이려고 그러는 거지.", en: "He’s trying to show off to impress some girls.", source: "Day 080 순한맛", meaning: meanings["show off_1"] },
        { week: 16, ko: "남자가 밤새 자기 자랑을 하더라고.", en: "The guy just bragged about himself the whole night.", source: "Day 080 순한맛", meaning: meanings["brag about_1"] },

        // Week 17
        { week: 17, ko: "게으름 피우지 않으려고 노력 중입니다.", en: "I’ve been trying to stop slacking off.", source: "Day 081 순한맛", meaning: meanings["slack off_1"] },
        { week: 17, ko: "매출이 주춤하고 있습니다.", en: "Sales are slacking off.", source: "Day 081 순한맛", meaning: meanings["slack off_2"] },
        { week: 17, ko: "재활용품을 분류해야 해.", en: "Sort out all the recycling before going outside.", source: "Day 082 순한맛", meaning: meanings["sort out_1"] },
        { week: 17, ko: "물건들을 좀 정리해야겠어.", en: "My room is a terrible mess, so I need to sort it out.", source: "Day 082 순한맛", meaning: meanings["sort out_2"] },
        { week: 17, ko: "다 잘 해결된 거야?", en: "Did you get everything sorted out?", source: "Day 082 순한맛", meaning: meanings["sort out_3"] },
        { week: 17, ko: "최대한 빨리 휴가 일정을 짜야 해.", en: "We need to sort out our holiday itinerary as soon as possible.", source: "Day 082 순한맛", meaning: meanings["sort out_4"] },
        { week: 17, ko: "좀 더 앉아 있다가 가자.", en: "Let’s stick around for a while.", source: "Day 083 순한맛", meaning: meanings["stick around_1"] },
        { week: 17, ko: "냄새가 몇 시간이나 남아 있거든요.", en: "The smell still sticks around for hours.", source: "Day 083 순한맛", meaning: meanings["stick around_2"] },
        { week: 17, ko: "가상현실 홈트레이닝이 그리 오래갈 것 같지는 않다.", en: "I don’t think they’ll stick around for long.", source: "Day 083 순한맛", meaning: meanings["stick around_3"] },
        { week: 17, ko: "끝까지 포기하지 않으면 정규직이 될 거야.", en: "All you need to do is stick it out until the end and you’ll be a full-time employee.", source: "Day 084 순한맛", meaning: meanings["stick it out_1"] },
        { week: 17, ko: "그냥 어떻게든 이겨 내는 수밖에 없대.", en: "She basically just said that my wife needs to tough it out.", source: "Day 084 순한맛", meaning: meanings["tough it out_1"] },
        { week: 17, ko: "은행에 들러 현금 좀 찾아 올 수 있을까?", en: "Could you stop by the bank and get some cash?", source: "Day 085 순한맛", meaning: meanings["stop by_1"] },
        { week: 17, ko: "시간 될 때 들러.", en: "You should come by for a visit sometime.", source: "Day 085 순한맛", meaning: meanings["come by_1"] },
        { week: 17, ko: "세탁소에 들러서 제 양복 좀 찾아 주실 수 있을까요?", en: "Could you please drop by the cleaners and pick up my suit?", source: "Day 085 순한맛", meaning: meanings["drop by_1"] },
        { week: 17, ko: "네가 들러 주면 좋겠어, 안 바쁘면.", en: "It’d be nice if you could swing by, if you’re not busy.", source: "Day 085 순한맛", meaning: meanings["swing by_1"] }
    ];

    // 2. 구동사 매운맛 (Week 13~17)
    const phrasalHard = [
        // Week 13
        { week: 13, ko: "아빠가 쓰는 공구들 가지고 장난 그만 좀 쳐! 위험한 것들이 있단 말이야.", en: "Don’t mess around with your dad’s tools! Some of them are dangerous.", source: "Day 061 교재1", meaning: meanings["mess around_1"] },
        { week: 13, ko: "제가 음악가는 아니지만 시간이 날 때면 드럼을 가지고 노는 걸 좋아합니다.", en: "I’m not a musician, but I like to mess around with the drums when I can.", source: "Day 061 교재1", meaning: meanings["mess around_1"] },
        { week: 13, ko: "오후 내내 보고서 마무리는 안 하고 휴대폰 하는 데 시간을 허비했다.", en: "I spent the whole afternoon messing around with my phone instead of finishing my report.", source: "Day 061 교재1", meaning: meanings["mess around_2"] },
        { week: 13, ko: "미안해. (네) 기분 상하게 할 의도는 없었어. 그냥 장난친 거라고.", en: "I’m sorry. I didn’t mean for you to take that as an insult. I was just trying to mess around.", source: "Day 061 교재1", meaning: meanings["mess around_3"] },
        { week: 13, ko: "그 둘은 그냥 재미로 만나는 거야. 둘 다 당장은 사귄다는 걸 알릴 마음이 없어.", en: "They’re just messing around; neither of them is planning on making it official anytime soon.", source: "Day 061 교재1", meaning: meanings["mess around_4"] },
        { week: 13, ko: "휴대폰 그만 만지작거려. 이제 자러 가야 할 시간이야.", en: "Stop messing around with your phone. It’s time to go to bed.", source: "Day 061 교재1", meaning: meanings["mess around_1"] },
        { week: 13, ko: "제 아들이 시험공부를 해야 함에도 비디오 게임을 하면서 계속 빈둥거리네요.", en: "My son keeps messing around with video games when he should be studying for his exams.", source: "Day 061 교재1", meaning: meanings["mess around_2"] },
        { week: 13, ko: "Andrew, 동생 좀 그만 놀리렴. 또 한 번 울리면 아빠한테 이른다.", en: "Stop messing around with your brother, Andrew. If you make him cry again, I’m telling your dad.", source: "Day 061 교재1", meaning: meanings["mess around_3"] },
        { week: 13, ko: "이제 여러 이성을 만나는 것도 지겹습니다. 정착해서 몇 년 안에 결혼하고 싶네요.", en: "I am tired of messing around. I want to settle down and get married within the next few years.", source: "Day 061 교재1", meaning: meanings["mess around_4"] },
        { week: 13, ko: "너희들 그룹 프로젝트 마무리하는 데 얼마나 걸렸어?", en: "How long did it take for you guys to finish the group project?", source: "Day 061 교재2", meaning: null },
        { week: 13, ko: "10시간 정도. 근데 계속해서 작업을 한 건 아니야. 끝나갈 무렵에는 슬슬 놀면서 했어.", en: "About 10 hours, but it wasn’t like we were working the whole time. Near the end, we were pretty much just messing around.", source: "Day 061 교재2", meaning: meanings["mess around_2"] },
        { week: 13, ko: "정말 이 머리 스타일 나한테 안 어울리는 거 같아? 여자 친구는 귀엽다고 했거든.", en: "Do you really think this hairstyle looks bad on me? My girlfriend said it looks cute.", source: "Day 061 교재2", meaning: null },
        { week: 13, ko: "아니야. 그냥 농담한 거야. 귀여워.", en: "No. I was just messing around. It’s cute.", source: "Day 061 교재2", meaning: meanings["mess around_3"] },
        { week: 13, ko: "이제 더 이상 이런 연애 안 할래. 나랑 결혼 안 할 거면 우리 끝내자.", en: "I am done messing around. If you are not going to marry me, then we are through.", source: "Day 061 교재2", meaning: meanings["mess around_4"] },
        { week: 13, ko: "내가 결혼을 원하지 않는다고 해서 집중을 안 하는 건 아니잖아. 결혼하지 않고도 서로에게 충실할 수는 없을까?", en: "Just because I don’t want to get married, that doesn’t mean I’m messing around. Can’t we be committed to each other without making things official?", source: "Day 061 교재2", meaning: meanings["mess around_4"] },
        { week: 13, ko: "자, 이제 신년도 되었으니 나쁜 습관 세 가지를 고치기로 결심했다.", en: "Well, it’s the start of a new year, and I’ve decided to work on three of my bad habits.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "우선 나는 회사에 제시간에 출근하는 것을 정말 못한다.", en: "First of all, I’m terrible at getting to work on time.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "늦는 경우가 많아서 이 때문에 여러 번 지적을 받았다.", en: "I’m usually late and have been reprimanded multiple times because of it.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "솔직히 출근하기가 너무 싫어서 출근 전에 30분 정도 뭉그적거리는 버릇이 있다.", en: "Honestly, before leaving for work, I tend to mess around for like 30 minutes because I just don’t want to go.", source: "Day 061 교재3", meaning: meanings["mess around_2"] },
        { week: 13, ko: "두 번째로 여가 시간을 좀 더 효과적으로 보낼 필요가 있다.", en: "Second, I need to use my free time more effectively.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "최근에는 퇴근 후에 아무 생각 없이 유튜브를 보거나 SNS를 하게 된다.", en: "Lately, when I get home from work, I just end up mindlessly watching YouTube or checking social media.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "이런 무의미한 시간을 좀 더 나은 사람이 될 수 있는 취미에 쓰면 더 좋다는 것을 알고 있다. 하지만 노력을 해도 잘 안된다.", en: "I know my time could be better spent on hobbies that make me a better person, but I just can’t get myself to do them.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "마지막으로 제때 취침을 해야겠다.", en: "Last, I’m going to start going to bed on time.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "수면 부족으로 건강이 나빠지고 있다.", en: "A lack of sleep has been taking a toll on my health.", source: "Day 061 교재3", meaning: null },
        { week: 13, ko: "공연 때 대사 몇 개를 잘못 말했지 뭐야.", en: "During the play, I messed up several of my lines.", source: "Day 062 교재1", meaning: meanings["mess up_1"] },
        { week: 13, ko: "올림픽에서는 설사 실수를 하더라도 아무 일 없었다는 듯 행동해야 해.", en: "When you mess up in the Olympics, you’re supposed to act gracefully about it.", source: "Day 062 교재1", meaning: meanings["mess up_1"] },
        { week: 13, ko: "내가 제일 좋아하는 음식이 프라이드치킨인데, 먹을 때마다 속이 뒤집어진다는 점이 문제야.", en: "My favorite food is fried chicken, but it messes up my stomach every time.", source: "Day 062 교재1", meaning: meanings["mess up_2"] },
        { week: 13, ko: "연습하는 동안 계속 이 춤 동작을 실수하게 된다. 이번 주말 무대에서도 내가 실수할까 봐 우리 팀원들이 걱정하고 있다.", en: "I keep messing up this particular dance move during practice. My team is getting worried that I might mess up on stage this weekend, too.", source: "Day 062 교재1", meaning: meanings["mess up_1"] },
        { week: 13, ko: "내 머리 좀 만지지 마. (자꾸 만지면) 엉망이 될 거야. 아침에 20분이나 들여서 머리 예쁘게 만졌단 말이야.", en: "Stop touching my hair. You are gonna mess it up. I spent 20 minutes this morning getting it just right.", source: "Day 062 교재1", meaning: meanings["mess up_2"] },
        { week: 13, ko: "그가 취소하는 바람에 제 스케줄 전체가 꼬여 버렸습니다.", en: "His cancellation has messed up my whole schedule.", source: "Day 062 교재1", meaning: meanings["mess up_2"] },
        { week: 13, ko: "예상치 못한 일이 생겨 일상이 꼬이는 건 싫다.", en: "I don’t like when unexpected things mess up my routine.", source: "Day 062 교재1", meaning: meanings["mess up_2"] },
        { week: 13, ko: "Nick, 나 실수한 것 같아. 여자 친구에게 내 폰을 보여 주고 있는데, 다른 여자가 내게 메시지를 보냈어.", en: "Nick, I think I messed up. While I was letting my girlfriend look at my phone, another girl messaged me.", source: "Day 062 교재2", meaning: meanings["mess up_1"] },
        { week: 13, ko: "버너폰을 가지고 다녀야 한다고 내가 말했잖아!", en: "I told you to carry a burner phone!", source: "Day 062 교재2", meaning: null },
        { week: 13, ko: "생일이라고 해서 케이크를 만들어 주려 하다가, 베이킹파우더를 너무 많이 넣는 바람에 망쳤네요.", en: "I tried to make you a cake for your birthday, but I messed it up by putting in too much baking powder.", source: "Day 062 교재2", meaning: meanings["mess up_1"] },
        { week: 13, ko: "그래도 만들어 주려고 한 게 정말 고맙군요. 이 케이크 너무 “고마워서” 먹을 수가 없네요. 대신 아이스크림 먹으러 가요.", en: "How sweet of you for trying, though. I “appreciate” this cake too much to eat it. Let’s go get ice cream, instead.", source: "Day 062 교재2", meaning: null },
        { week: 13, ko: "아메리카노 사 왔어.", en: "I bought you an Americano.", source: "Day 062 교재2", meaning: null },
        { week: 13, ko: "아, 미안해. 나 커피 마시면 안 돼. 커피를 안 좋아하는 게 아니고, 카페인을 섭취하면 머리가 아프거든.", en: "Oh, I’m sorry. I can’t have any coffee. It’s not that I don’t like coffee. It’s just that caffeine messes me up.", source: "Day 062 교재2", meaning: meanings["mess up_2"] },
        { week: 13, ko: "나는 해외여행을 할 때 시차 때문에 힘든 일이 잘 없다.", en: "I normally don’t suffer from jet lag when I travel abroad.", source: "Day 062 교재3", meaning: null },
        { week: 13, ko: "이유는 잘 모르겠지만, 아마 다른 나라에 간다는 게 너무 설레서일지도 모르겠다.", en: "I’m not sure why, though; maybe because I’m always excited to be in a different country.", source: "Day 062 교재3", meaning: null },
        { week: 13, ko: "하지만 지난달 사장님으로부터 업무 회의차 토론토 출장을 가야 한다는 말을 들었고, 그날 밤 바로 출발해야 한다고 했다.", en: "However, last month I was told by my boss that I needed to fly to Toronto for a business conference, and that I would need to leave that night.", source: "Day 062 교재3", meaning: null },
        { week: 13, ko: "회의 준비는커녕 집에 가서 짐을 챙길 시간도 거의 없었다.", en: "I barely had time to go home and pack, let alone prepare for business meetings.", source: "Day 062 교재3", meaning: null },
        { week: 13, ko: "4일 동안 토론토에 있었고 회의는 잘 끝났지만, 출장에서 돌아온 후 계속 수면이 엉망인 상태가 이어지고 있다.", en: "I was there for four days and the meetings went fine, but my sleep has been messed up ever since I got back.", source: "Day 062 교재3", meaning: meanings["mess up_2"] },
        { week: 13, ko: "음악 좀 바꿔 줄래? 기분이 우울해지잖아.", en: "Can you change the music? It’s messing with my mood.", source: "Day 063 교재1", meaning: meanings["mess with_1"] },
        { week: 13, ko: "더 이상 Brandon이랑은 엮이기 싫어(안 놀아). 내 화를 돋워 싸움을 시작하게 하는 말만 한다니까.", en: "I don’t mess with Brandon anymore. He knows exactly what to say to rile me up and start a fight.", source: "Day 063 교재1", meaning: meanings["mess with_2"] },
        { week: 13, ko: "저는 출근할 때 더 이상 버스는 안 탑니다. 예측이 어렵고 (버스 타서) 지각한 적이 너무 많습니다.", en: "I don’t mess with the bus system anymore to get to work. It’s unpredictable and it made me late too many times.", source: "Day 063 교재1", meaning: meanings["mess with_2"] },
        { week: 13, ko: "그냥 한 말이야. 너무 예민하게 굴지 마.", en: "I was just messing with you. Don’t be so sensitive.", source: "Day 063 교재1", meaning: meanings["mess with_3"] },
        { week: 13, ko: "이봐, 내 카메라 설정 건드린 거야? 새로 찍은 사진이 죄다 과다 노출로 나오잖아.", en: "Hey, did you mess with the settings on my camera? All my new photos are overexposed.", source: "Day 063 교재1", meaning: meanings["mess with_4"] },
        { week: 13, ko: "늦은 시간에 커피 마시지 말아야겠어. 수면에 방해가 돼.", en: "I have to stop drinking coffee late; it messes with my sleep.", source: "Day 063 교재1", meaning: meanings["mess with_1"] },
        { week: 13, ko: "더 이상 술은 안 마십니다. 술 마셔서 좋을 게 하나도 없는 것 같아서요.", en: "I don’t mess with alcohol anymore. It just seems like nothing good ever comes out of drinking.", source: "Day 063 교재1", meaning: meanings["mess with_2"] },
        { week: 13, ko: "식중독 걸린 이후로는 여행 중에 길거리 음식은 안 먹습니다.", en: "Ever since I got food poisoning, I don’t mess with street food on my travels.", source: "Day 063 교재1", meaning: meanings["mess with_2"] },
        { week: 13, ko: "제 친구는 자기가 일본인인 양 메뉴판을 읽지 못하는 척하면서 식당 직원을 골탕 먹이는 버릇이 있습니다. 멍청한 녀석이죠.", en: "My friend likes to mess with servers by pretending he’s Japanese and can’t read the menu. He’s kind of a jerk.", source: "Day 063 교재1", meaning: meanings["mess with_3"] },
        { week: 13, ko: "내가 나가 있는 동안 누가 내 태블릿 건드린 거야? 내가 다운 받지도 않은 앱이 엄청 있네.", en: "Who messed with my new tablet while I was gone? There’s a bunch of apps that I didn’t download on it.", source: "Day 063 교재1", meaning: meanings["mess with_4"] },
        { week: 13, ko: "주방에 있는 분은 건드리면 안 된다는 걸 비싼 대가를 치르고 알게 되었어요. 다음 날 식중독으로 병원 신세를 지게 되었습니다.", en: "I learned the hard way not to mess with kitchen staff. I ended up in the hospital with food poisoning the next day.", source: "Day 063 교재1", meaning: meanings["mess with_5"] },
        { week: 13, ko: "다음 …시에 …하자, …알았지?", en: "Let’s… at… o’clock… next… okay?", source: "Day 063 교재2", meaning: null },
        { week: 13, ko: "뭐라고? 끊겨서 들려. 지하라서 신호가 끊기는 것 같아. 내려서 다시 전화할게.", en: "Sorry? You’re breaking up. I think being underground is messing with my signal. I’ll call you back when I get off.", source: "Day 063 교재2", meaning: meanings["mess with_1"] },
        { week: 13, ko: "내일 만우절이라 학생들 좀 골탕 먹이려고요.", en: "I am going to mess with my students tomorrow for April Fool’s Day.", source: "Day 063 교재2", meaning: meanings["mess with_3"] },
        { week: 13, ko: "진짜요? 어떤 계획인가요? 저도 같이 아이들 놀려 볼까 싶네요.", en: "Oh really? What do you have planned? Maybe I’ll get in on it with you.", source: "Day 063 교재2", meaning: null },
        { week: 13, ko: "Johnny가 뭐라고 했는지 들었어? 누가 걔 좀 혼내 줘야 해.", en: "Did you hear what Johnny said? Someone should teach him a lesson.", source: "Day 063 교재2", meaning: null },
        { week: 13, ko: "걔는 건들지 마. 이 동네에서 제일 센 녀석들이랑 친구니까.", en: "Don’t mess with him. He’s friends with some of the strongest guys in town.", source: "Day 063 교재2", meaning: meanings["mess with_5"] },
        { week: 13, ko: "안녕하세요, 여러분! 오 박사님이 오늘 함께 해 주셨습니다. 알코올 섭취와 과음의 기준에 대해 한 말씀해 주실 겁니다. 박사님, 시작하시죠.", en: "Hello, everyone! Dr. Oh is with us today to teach us a bit about alcohol consumption, and how much is too much. Doctor, please go ahead.", source: "Day 063 교재3", meaning: null },
        { week: 13, ko: "감사합니다. 아시다시피 많은 한국인이 퇴근 후 술 한잔하면서 긴장을 푸는 것을 좋아하지만, 문제는 말씀하신 것처럼, 어느 정도가 과한 것일까요?", en: "Thank you. As we all know, a lot of Koreans like to kick back with a few drinks after getting off work, but the question is, as you said, how much is too much?", source: "Day 063 교재3", meaning: null },
        { week: 13, ko: "사실 술은 조금만 마신다고 해도 너무 자주 마실 경우에는 건강에 해롭습니다.", en: "Actually, consuming even a little alcohol too frequently can have negative effects on our health.", source: "Day 063 교재3", meaning: null },
        { week: 13, ko: "우선 수면의 질을 떨어뜨립니다.", en: "First and foremost, alcohol really messes with your quality of sleep.", source: "Day 063 교재3", meaning: meanings["mess with_1"] },
        { week: 13, ko: "술을 먹어야겠다면 주 1회로 제한해야 하고, 적당히 마셔야 합니다.", en: "If you feel the need to indulge, you should limit yourself to drinking once a week, and in moderation.", source: "Day 063 교재3", meaning: null },
        { week: 13, ko: "오늘 밤에 나와. 파티 안 가면 후회할 거야.", en: "Hey, come out tonight. You don’t want to miss the party.", source: "Day 064 교재1", meaning: null },
        { week: 13, ko: "A: 아파서 지난 주말 콘서트에 못 갔다며. 맞아?", en: "A: I heard you were sick and couldn’t make it to the concert last weekend. Is that right?", source: "Day 064 교재1", meaning: null },
        { week: 13, ko: "B: 응. 정말 가고 싶었는데 전날 독감에 걸렸어.", en: "B: Yeah. I was really looking forward to it, but I got the flu the day before.", source: "Day 064 교재1", meaning: null },
        { week: 13, ko: "A: 정말 안됐다! 너무 좋은 기회를 놓쳤네! 정말 멋진 시간이었는데.", en: "A: Too bad! You really missed out! It was an amazing time.", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "지민 씨, 토요일 회의하기 전에 아팠다면서요. 걱정 마세요. (회의 때) 이렇다 할 특별한 내용은 없었어요.", en: "Hey Jimin, I heard you got sick before Saturday’s meeting. Don’t worry. You didn’t miss out on anything.", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "파티를 즐길 수 있는 기회 혹은 상사랑 술 마실 수 있는 기회를 놓치고 싶지 않거든.", en: "I don’t want to miss out on the party or on getting to drink with the boss.", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "A: 우리 가족들이 하와이에 가는데, 나는 일이 바쁘다고 했어.", en: "A: My family is going to Hawaii, but I told them I was too busy at work.", source: "Day 064 교재1", meaning: null },
        { week: 13, ko: "B: 뭐라고? 하와이 여행을 마다하는 게 말이 돼?", en: "B: What? Why would you want to miss out on a trip to Hawaii?", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "이건 너무 중요한 기회야! 절대로 그냥 보내지 않을 거야.", en: "This is a huge chance! I’m not going to miss out on it.", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "아파서 스키 여행 갈 수 있는 기회를 놓치다니. 너무 속상해!", en: "I can’t believe I missed out on the ski trip because I was sick. What a bummer!", source: "Day 064 교재1", meaning: meanings["miss out_1"] },
        { week: 13, ko: "도산대로에서 하는 Montana Choi의 파티에 꼭 와. 인맥을 쌓을 수 있는 기회를 놓치면 안 되니까.", en: "You have to come to Montana Choi’s party on Dosan Street. You don’t want to miss out on a chance to network.", source: "Day 064 교재2", meaning: meanings["miss out_1"] },
        { week: 13, ko: "알아. 나도 꼭 가서 그분과 친해지고 싶었어. 근데 내 스케줄을 확실히 모르겠어. 수요일까지 알려줘도 돼?", en: "I know. I was really hoping to go and get acquainted with him. I’m still not sure about my schedule, though. Can I let you know by Wednesday?", source: "Day 064 교재2", meaning: null },
        { week: 13, ko: "회식은 나랑 안 맞아. 상사가 소주를 강요하는 게 너무 싫거든.", en: "Team dinners aren’t really for me. I don’t like that supervisors insist on me drinking soju.", source: "Day 064 교재2", meaning: null },
        { week: 13, ko: "나도 마찬가지야. 나도 회사 회식 가는 거 싫어. 그래도 흥미로운 소소한 이야기를 놓치고 싶지 않아서 여전히 가긴 해.", en: "Same here. I don’t like going out to company dinners, either. But I still go because I don’t want to miss out on the juicy small talk.", source: "Day 064 교재2", meaning: meanings["miss out_1"] },
        { week: 13, ko: "못 오실 줄 알았더니 오셔서 다행입니다. (이번 행사를) 꼭 경험하시길 바랐거든요. 멋진 안경도 보시고 패션 쪽 사람들과도 어울릴 좋은 기회일 거예요.", en: "Well, I’m glad you could make it. I didn’t want you to miss out. It will be a good chance to check out these amazing glasses and mingle with people in the fashion industry.", source: "Day 064 교재2", meaning: meanings["miss out_1"] },
        { week: 13, ko: "팝업 행사 초대해 줘서 고맙습니다. 진짜 기대했습니다. 그나저나 안경테 추천해 주실 만한 것 있을까요?", en: "Thanks for inviting me to the pop-up event. I was really looking forward to it. Are there any particular frames you would recommend, by the way?", source: "Day 064 교재2", meaning: null },
        { week: 13, ko: "아무래도 SNS를 완전히 끊어야 할 것 같다. 특히 인스타그램을 말이다.", en: "I feel like I should quit social media altogether, especially Instagram.", source: "Day 064 교재3", meaning: null },
        { week: 13, ko: "친구들이 끊임없이 휴가를 보내거나 밤에 나가서 노는 걸 보면 다른 사람들은 인생을 충분히 즐기는데 나만 소외된 느낌이 든다.", en: "Seeing my friends constantly on holiday or enjoying nights out can make me feel like I am missing out while others are living their life to the fullest.", source: "Day 064 교재3", meaning: meanings["miss out_1"] },
        { week: 13, ko: "최근 우연히 보게 된 기사를 한번 보자.", en: "Take a look at this article I recently came across.", source: "Day 064 교재3", meaning: null },
        { week: 13, ko: "내용은 이렇다. “SNS는 사람들에게 비현실적인 기대를 갖게 하고, 자존감이 낮아지게 만든다. 인스타그램 때문에 여성들이 자신의 외모가 부족하다고 느끼게 된다.”", en: "It goes like this: “Social media posts can also set unrealistic expectations and create feelings of low self-esteem. Instagram easily makes girls and women feel as if their bodies aren’t good enough.”", source: "Day 064 교재3", meaning: null },
        { week: 13, ko: "여성으로서 이 기사에서 여자가 한 말에 너무 공감이 간다. 여러분은 어떤가?", en: "As a woman, I couldn’t agree more with what she said in the article. How do you feel?", source: "Day 064 교재3", meaning: null },
        { week: 13, ko: "A: Haley, 어젯밤 데이트는 어땠어?", en: "A: Haley, how was your date last night?", source: "Day 065 교재1", meaning: null },
        { week: 13, ko: "B: 너무 좋았어. 저녁 먹고, 조용한 와인바로 이동해서 몇 시간 동안 이야기를 나누었어. 이 남자가 내가 찾던 남자라는 생각이 들어.", en: "B: It was amazing. We had dinner and moved on to a quiet wine bar where we talked for hours. I really think this guy is the one.", source: "Day 065 교재1", meaning: meanings["move on_1"] },
        { week: 13, ko: "지하철에서 우연히 전 여자 친구를 마주쳤는데도 아무렇지도 않더군요. 그제서야 이제는 잊고 새출발해도 되겠구나 싶었습니다.", en: "I knew I was ready to move on when I ran into my ex on the subway and I felt completely normal around her.", source: "Day 065 교재1", meaning: meanings["move on_3"] },
        { week: 13, ko: "저는 하나의 업무를 완료하지 못하면 다음 일로 넘어가지 못하는 사람입니다. 멀티태스킹에 능한 사람이 아닙니다.", en: "I’m the kind of person who can’t move on until I completely finish a task. I’m not a multi-tasker.", source: "Day 065 교재1", meaning: meanings["move on_2"] },
        { week: 13, ko: "뉴욕에 3년 살았는데, 정말 좋은 경험이었습니다. 하지만 이젠 다른 도시에 가서 살 때가 된 것 같아요.", en: "I’ve lived in New York for three years and I’m really glad for the experience. But now, I think I am ready to move on.", source: "Day 065 교재1", meaning: meanings["move on_3"] },
        { week: 13, ko: "답을 모르겠으면, 다음 문제로 넘어갔다가 쉬운 것을 다 풀고 난 후에 다시 풀어 봐.", en: "When you don’t know the answer to a question, move on and try again when you’ve finished the easier ones.", source: "Day 065 교재1", meaning: meanings["move on_2"] },
        { week: 13, ko: "Sarah가 이번 주말에 소개팅하기로 했어. 전 남자 친구를 굉장히 빨리 잊는 것 같아.", en: "Sarah’s going on a blind date this weekend. I guess she moves on really fast.", source: "Day 065 교재1", meaning: meanings["move on_3"] },
        { week: 13, ko: "스캔들 이후에 그의 팬 중 많은 이들의 마음이 이미 떠난 상태다.", en: "Following the scandal, many of his fans have already moved on.", source: "Day 065 교재1", meaning: meanings["move on_4"] },
        { week: 13, ko: "이제 다음으로 넘어가도 될 것 같네요. 다음 슬라이드 띄우겠습니다.", en: "I think we’re ready to move on, so I’ll just pull up the next slide.", source: "Day 065 교재2", meaning: meanings["move on_2"] },
        { week: 13, ko: "잠시만요. 배터리 셀 부분을 좀 더 자세히 설명해 주실 수 있을까요? 그 부분이 조금 이해가 안 돼서요.", en: "Wait a second. Can you elaborate more on battery cells? You lost me a bit there.", source: "Day 065 교재2", meaning: null },
        { week: 13, ko: "어젯밤에 Jeff랑 Hailey를 데리고 나가서 저녁 식사했다면서? 어땠어? 오늘 아침에 보니 Jeff 몰골이 말이 아니던데.", en: "I heard you took Jeff and Hailey out to dinner last night. How did it go? Jeff was looking pretty rough this morning when I saw him.", source: "Day 065 교재2", meaning: null },
        { week: 13, ko: "응, 맞아. 1차로 삼겹살 먹고 2차는 공덕역에 있는 ‘언포게터블’이라는 바에 갔어. Jeff가 고주망태가 되어 여자들에게 추파를 던지기 전까지는 좋았는데 말이야. Hailey는 엄청 화가 났지.", en: "Yeah, I did. We first went out for pork belly before moving on to a bar named “Unforgettable” at Gongdeok station. We were having a good time until Jeff got totally wasted and started hitting on some women. Hailey was furious.", source: "Day 065 교재2", meaning: meanings["move on_1"] },
        { week: 13, ko: "아직 지원이에게 감정이 남아 있는 거니? 벌써 6개월이 지났잖아. 과거에 연연하지 말고 새출발해야지.", en: "Are you still upset about Jiwon? It’s been six months already. You can’t let the past get in the way. It’s time to move on.", source: "Day 065 교재2", meaning: meanings["move on_3"] },
        { week: 13, ko: "그게 말처럼 쉽지가 않아. 그녀를 잊을 수가 없어. 헤어진 건 너무 큰 실수였다는 생각 밖에 안 들어.", en: "I wish it was that easy. I can’t get over her. All I can think about is what a huge mistake I made.", source: "Day 065 교재2", meaning: null },
        { week: 13, ko: "예전에는 Lady Gaga의 엄청난 팬이었다. 하지만 최근 앨범은 그냥 쉽게 돈 벌려고 만든 느낌이다.", en: "I used to be a huge fan of Lady Gaga, but her latest album just feels like a cash grab.", source: "Day 065 교재3", meaning: null },
        { week: 13, ko: "이제 그녀의 전성기는 끝난 것 같다. 왜 많은 팬들이 마음이 떠나고 있는지 알겠다.", en: "It looks like her peak time in the spotlight is over, and I can see why many fans are moving on.", source: "Day 065 교재3", meaning: meanings["move on_4"] },
        { week: 13, ko: "그녀는 더 이상 음악계에서 의미 있는 역할을 하지 못하는 듯하다.", en: "She just doesn’t seem to play a real role in the music scene anymore.", source: "Day 065 교재3", meaning: null },
        { week: 13, ko: "팬들과도 너무 동떨어져 있는 것 같다. 특히 SNS에서의 적극적인 활동이 너무 부족하다.", en: "It seems like she’s lost touch with fans, especially with her lack of engagement on social media.", source: "Day 065 교재3", meaning: null },
        { week: 13, ko: "최근에는 예술적인 완성도를 유지하기보다는 돈 버는 데 더 집중하는 것 같아서, 정말 실망스럽다.", en: "Lately, it feels like she’s more focused on making money than maintaining her artistic integrity, which has really disappointed me.", source: "Day 065 교재3", meaning: null },

        // Week 14
        { week: 14, ko: "내 의상 어때? 진짜 경찰관처럼 보일까?", en: "What do you think of my costume? Could I pass for a real police officer?", source: "Day 066 교재1", meaning: meanings["pass for_1"] },
        { week: 14, ko: "네가 수염 기르면 아빠라고 해도 믿을 거야.", en: "If you grew a mustache, you could definitely pass for your dad.", source: "Day 066 교재1", meaning: meanings["pass for_1"] },
        { week: 14, ko: "제가 이 조선시대 가구의 복제품을 가지고 있는데, 대부분 사람들은 진짜 골동품이라고 해도 믿을 겁니다.", en: "I have this replica piece of Joseon Dynasty furniture. It could definitely pass for an authentic antique to most people.", source: "Day 066 교재1", meaning: meanings["pass for_1"] },
        { week: 14, ko: "그는 정상적인 은행원이자 남편인 척 거짓 삶을 살았다. 아무도 그가 사이코패스인 줄은 몰랐다.", en: "He was living his life, passing for a normal banker and husband. No one knew he was actually a psychopath.", source: "Day 066 교재1", meaning: meanings["pass for_2"] },
        { week: 14, ko: "민수는 영어를 너무 잘해서 재미 교포라고 해도 믿을 것이다.", en: "Minsu’s English is so good that he can pass for a Korean-American.", source: "Day 066 교재1", meaning: meanings["pass for_1"] },
        { week: 14, ko: "굉장히 아껴 쓴 시계라 새 제품이라고 해도 믿을 겁니다. 박스 개봉하고 거의 사용하지 않았거든요.", en: "This gently-used watch could pass for new. It’s barely been out of its box.", source: "Day 066 교재1", meaning: meanings["pass for_1"] },
        { week: 14, ko: "저는 파리에서 자랐습니다. 어떤 곳이건 여행 중에 새로운 장소에서 튀지 않고 묻어 가는 건 어려울 수 있지만, 파리 현지인처럼 보이고 싶거나 편안한 여행을 원한다면 알아 둬야 할 몇 가지가 있습니다. 로지 베이커리에서는 가장 신선한 바게트를 살 수 있습니다. 친구들과 나눠 먹을 수 있는 타르트도 살 수 있고, 출근 전에 간단하게 먹을 크루아상을 살 수도 있으며, 방과 후 간식을 먹을 수 있는 곳이기도 합니다.", en: "I grew up in Paris. It can be difficult to fit into any new place while traveling, but there are a few things I think you should know if you’re trying to pass for a Paris local or simply want to have a smooth trip. The Rouge Bakery is where you can get the freshest baguettes. It’s also a spot to buy tarts to share with friends, grab a quick croissant before work, and eat a snack after school.", source: "Day 066 교재1", meaning: meanings["pass for_2"] },
        { week: 14, ko: "너 영어를 너무 잘해서 원어민이라고 해도 믿겠어. 영미권 국가에는 한 번도 안 가 봤다고 하지 않았니? 그럼 영어를 어디에서 익힌 거야?", en: "Your English is so good that you could almost pass for a native speaker. Didn’t you mention that you’ve never been to any English-speaking countries? Where did you pick up your English, then?", source: "Day 066 교재2", meaning: meanings["pass for_1"] },
        { week: 14, ko: "그렇게 말해 줘서 고마워. 주로 미드 보면서 익혔어. 근데 서울에 영국인 친구들도 좀 있어서 이 친구들과 어울린 게 큰 도움이 되었어.", en: "Thank you for saying so. I mostly picked it up from watching American shows, but I’ve got some British friends in Seoul, and hanging out with them has really helped.", source: "Day 066 교재2", meaning: null },
        { week: 14, ko: "그분이 50대 후반이라는 것이 믿기지 않아. 틀림없이 피부관리를 정말 잘했을 거야. 서른이라고 해도 믿겠다.", en: "I can’t believe she is in her late 50s. She obviously has taken such good care of her skin. She could even pass for 30.", source: "Day 066 교재2", meaning: meanings["pass for_1"] },
        { week: 14, ko: "내 말이. 보니까 강남에 있는 고급 피부과에서 비싼 시술을 받는 듯해. 나도 그럴 형편이 되면 좋으련만.", en: "Totally. Apparently, she is getting some expensive treatments from a posh skin clinic in Gangnam. I wish I could afford that, too.", source: "Day 066 교재2", meaning: null },
        { week: 14, ko: "수상 소감에 대한 그녀의 통역 어떻게 봤어?", en: "What did you think of her interpretation of his acceptance speech?", source: "Day 066 교재2", meaning: null },
        { week: 14, ko: "정말 대단하더라. 전문 통역사라고 해도 믿을 거야.", en: "I was blown away. I think she could pass for a professional interpreter.", source: "Day 066 교재2", meaning: meanings["pass for_1"] },
        { week: 14, ko: "지난 크리스마스 때 나는 아이들을 위해 산타 역할을 하고 싶었다. 하지만 그때가 (이미) 12월 하순이라 저렴한 중고 의상밖에 구할 수가 없었다.", en: "Last Christmas, I wanted to play Santa for the kids, but it was late December, and all I could get my hands on was a cheap, used costume.", source: "Day 066 교재3", meaning: null },
        { week: 14, ko: "크리스마스쯤에 는 산타 복장을 찾는 사람이 많기 때문에 아무리 늦어도 12월 초까지는 주문해야 한다.", en: "Santa costumes are in high demand around Christmas, so you should really order one by early December at the latest.", source: "Day 066 교재3", meaning: null },
        { week: 14, ko: "내가 들어가자마자 아이들이 (내가) 변장한 걸 알아차리면 어쩌나 정말 걱정되었다.", en: "I was really worried that my kids would see through the disguise as soon as I walked in.", source: "Day 066 교재3", meaning: null },
        { week: 14, ko: "수염은 대걸레 같아 보였고, 옷에는 심지어 진짜 단추도 없었다.", en: "The beard looked like a mop, and the suit didn’t even have real buttons.", source: "Day 066 교재3", meaning: null },
        { week: 14, ko: "그래도 산타 옷을 입었고, 끝까지 (들키지 않기를 바라는) 희망을 잃지 않았다.", en: "Still, I put on the costume and hoped for the best.", source: "Day 066 교재3", meaning: null },
        { week: 14, ko: "거실에 들어갔더니 아이들의 눈이 기대감으로 반짝였다.", en: "When I came into the living room, the kids’ eyes lit up with excitement.", source: "Day 066 교재3", meaning: null },
        { week: 14, ko: "의상은 형편없었지만, 다행히 산타인 척 속일 수 있었고, 그날 저녁은 정말 신비로운 밤이었다.", en: "Despite the bad costume, I managed to pass for Santa, and the evening was a magical one.", source: "Day 066 교재3", meaning: meanings["pass for_2"] },
        { week: 14, ko: "내 꿈의 차인 포르쉐 911을 살 수 있는 기회를 그냥 포기할 수밖에 없었다.", en: "I had to pass up (on) getting my dream car, a Porsche 911.", source: "Day 067 교재1", meaning: meanings["pass up_1"] },
        { week: 14, ko: "허리선이 너무 타이트해서 너무 멋진 청바지를 아쉬워하며 그냥 포기해야만 했던 적이 있나요?", en: "Have you ever had to pass up (on) a pair of jeans that looked great, only because the waist was too tight?", source: "Day 067 교재1", meaning: meanings["pass up_1"] },
        { week: 14, ko: "A: 왜 세 병이나 산 거야? 한 병만 있으면 되는데.", en: "A: Why did you buy three bottles? We only needed one.", source: "Day 067 교재1", meaning: null },
        { week: 14, ko: "B: ‘투 플러스 원’ 행사를 하더라고. 그냥 지나칠 수가 없었어.", en: "B: It was buy two, get one free. I couldn’t pass that up.", source: "Day 067 교재1", meaning: meanings["pass up_1"] },
        { week: 14, ko: "다이어트 중이긴 한데, 사무실에서 공짜 도넛을 주면 절대 그냥 넘어갈 수는 없지.", en: "I’m on a diet, but I can never pass up (on) free donuts at the office.", source: "Day 067 교재1", meaning: meanings["pass up_1"] },
        { week: 14, ko: "새 옷이 필요하지는 않았지만 세일하는 걸 그냥 지나칠 수가 없었다.", en: "Even though I didn’t need a new dress, I couldn’t pass up (on) the sale.", source: "Day 067 교재1", meaning: meanings["pass up_1"] },
        { week: 14, ko: "제가 Olivia Palermo 스타일에 푹 빠져 있어서, 그녀를 직접 만날 수 있는 기회를 그냥 보낼 수는 없었습니다.", en: "I’ve been obsessed with Olivia Palermo’s style for a while, so I couldn’t pass up (on) the chance to meet her in person!", source: "Day 067 교재1", meaning: meanings["pass up_1"] },
        { week: 14, ko: "안녕하세요. 우연히 이 덴마크산 의자를 봤는데요. 제가 정말 구하고 싶었던 겁니다. 표기된 가격보다 더 지불할 용의가 있습니다.", en: "Hello. I just came across this Danish chair, and it’s something I was really hoping to get my hands on. I would be willing to pay even more than the listed price.", source: "Day 067 교재2", meaning: null },
        { week: 14, ko: "제안 감사합니다만, 안타깝게도 이미 다른 분에게 팔기로 해서 제안을 고사해야 할 것 같습니다.", en: "Thank you for your offer, but unfortunately, I’ll have to pass it up because I already promised to sell the chair to someone else.", source: "Day 067 교재2", meaning: meanings["pass up_1"] },
        { week: 14, ko: "우와, 저 줄 좀 봐. 가서 무슨 일인지 한번 보자. (알고 보니 커피를 공짜로 나눠 주고 있었다.) 내가 공짜 커피는 절대로 그냥 지나치지 않지!", en: "Wow, check out that line. Let’s go over and check out what’s going on. (It turned out they were handing out free coffee.) I never pass up on free drinks!", source: "Day 067 교재2", meaning: meanings["pass up_1"] },
        { week: 14, ko: "친구야, 그냥 넘어가는 게 어때? 한국 속담에 이런 말이 있어. “공짜 좋아하면 대머리 된다.”", en: "Hey, dude, can’t we skip it? There is this saying in Korea. “If you go after only free things, you’ll lose your hair.”", source: "Day 067 교재2", meaning: null },
        { week: 14, ko: "너 이미 가죽 재킷 많잖아. 그냥 있는 걸로 버티지 그래?", en: "You already have enough leather jackets. Why don’t you just make do with what you already have?", source: "Day 067 교재2", meaning: null },
        { week: 14, ko: "응, 이미 많지. 근데 이 천연 가죽 재킷이 50만 원에 세일하는 걸 보니까 그냥 못 지나치겠더라고.", en: "Yeah, I know I already have enough, but when I saw this genuine leather jacket on sale for 500,000 won, I couldn’t pass it up.", source: "Day 067 교재2", meaning: meanings["pass up_1"] },
        { week: 14, ko: "29만 킬로미터를 탄 2006년산 시에나 구매에 대한 조언이 필요합니다", en: "Need advice on buying a 2006 Sienna with 290,000 km", source: "Day 067 교재3", meaning: null },
        { week: 14, ko: "안녕하세요. 이곳은 처음입니다. 포스팅을 해도 될지는 잘 모르겠지만, 저는 믿을만한 밴을 알아보고 있는 중년 여성입니다. 차 관리에 대해서는 잘 모르고요.", en: "Hi, I’m new here. I don’t know if this is OK to post, but I’m an older woman who is trying to find a dependable van, and I don’t know much about car maintenance.", source: "Day 067 교재3", meaning: null },
        { week: 14, ko: "내일 차를 보러 가기로 예약해 두었습니다. 이 차는 주행거리가 29만 킬로미터 정도 된 차입니다.", en: "I have an appointment to look at a car tomorrow with about 290,000 km on it.", source: "Day 067 교재3", meaning: null },
        { week: 14, ko: "관리를 잘 한 것 같고 상태도 좋아 보입니다.", en: "It seems well-maintained, and looks fine.", source: "Day 067 교재3", meaning: null },
        { week: 14, ko: "정비사가 차 상태를 확인할 예정이지만, 제가 보기에는 타이밍 벨트를 교체할 시점이 된 것 같습니다.", en: "I’m having a mechanic check it out, but from what I can tell, the timing belt probably needs replacing about now, right?", source: "Day 067 교재3", meaning: null },
        { week: 14, ko: "차주는 제가 차를 보기도 전에 가격을 530만 원에서 340만 원으로 깎아 주었습니다.", en: "The owner gave me a discount on the price from 5.3 million won to 3.4 million won before I even took a look at it.", source: "Day 067 교재3", meaning: null },
        { week: 14, ko: "이 차가 내년에 수리비로 수백만 원이 들어가는 건 아닌지 궁금합니다.", en: "I just wanted to know if it’s going to end up costing me millions in maintenance over the next year.", source: "Day 067 교재3", meaning: null },
        { week: 14, ko: "그럴 경우 (아쉽지만) 이번 기회를 그냥 보내야 할 것 같고요. 그래도 좋은 밴인 것 같기는 합니다.", en: "If so, I will have to pass it up, even though it looks like a nice van.", source: "Day 067 교재3", meaning: meanings["pass up_1"] },
        { week: 14, ko: "결국 제가 계산을 해 버렸어요.", en: "I ended up picking up the tab.", source: "Day 068 교재1", meaning: null },
        { week: 14, ko: "뭐 좀 사다 줄까?", en: "Do you want me to pick anything up for you?", source: "Day 068 교재1", meaning: meanings["pick up_3"] },
        { week: 14, ko: "집에 가는 길에 저녁거리 좀 사 갈게.", en: "I’ll pick up something for dinner on my way home.", source: "Day 068 교재1", meaning: meanings["pick up_3"] },
        { week: 14, ko: "몽골 여행 중에 우연찮게 한국에는 없는 산자나무 열매 잼을 사게 됐다.", en: "On our trip to Mongolia, we picked up sea buckthorn jam, which isn’t available back home.", source: "Day 068 교재1", meaning: meanings["pick up_3"] },
        { week: 14, ko: "원두는 쏟으면 줍기가 (너무) 번거롭다. 튀어서 여기저기 가 버린다.", en: "Coffee beans are a hassle to pick up if you spill them. They bounce and end up going everywhere.", source: "Day 068 교재1", meaning: meanings["pick up_1"] },
        { week: 14, ko: "내가 회사로 태우러 갈게.", en: "I will pick you up from work.", source: "Day 068 교재1", meaning: meanings["pick up_2"] },
        { week: 14, ko: "CU에서 커피 살 건데, 너도 필요하니?", en: "I’ll pick up some coffee at the CU. Would you like some?", source: "Day 068 교재1", meaning: meanings["pick up_3"] },
        { week: 14, ko: "A: ‘킬로미터’를 ‘clicks’로 표현하는 분은 당신이 처음이네요.", en: "A: You’re the first person I’ve heard use the word “clicks” for “kilometers.”", source: "Day 068 교재1", meaning: null },
        { week: 14, ko: "B: 네, 회사에 캐나다 분들이 있는데 그분들 때문에 그렇게 표현하게 된 것 같아요.", en: "B: Yeah, I think I picked up that expression from the Canadians in my office.", source: "Day 068 교재1", meaning: meanings["pick up_4"] },
        { week: 14, ko: "여러분, 어제 마친 부분부터 다시 이야기할까요?", en: "OK, guys, let’s pick up where we left off yesterday.", source: "Day 068 교재1", meaning: meanings["pick up_5"] },
        { week: 14, ko: "그거 고수야? 으으… 내가 고수 별로 안 좋아한다고 말하지 않았나? 그나저나 어디서 산 거야? 신선한 고수를 찾기 힘들거든.", en: "Is that cilantro? Ugh… didn’t I mention that I don’t really care for cilantro? Where did you pick that up, by the way? It’s kind of hard to find fresh cilantro.", source: "Day 068 교재2", meaning: meanings["pick up_3"] },
        { week: 14, ko: "앗, 완전 깜박했다. 숙대입구역 바로 옆에 채소 가게가 있어.", en: "Oh, dang it. That totally slipped my mind. There is this produce store right next to Sookmyung Women’s University station.", source: "Day 068 교재2", meaning: null },
        { week: 14, ko: "맛있는 올리브 치즈 빵 사 왔어. 먹어 볼래? 대전에 출장 갈 때마다 성심당에서 빵을 사거든.", en: "I got you this delicious olive cheese bread. Wanna try some? Whenever I go to Daejeon for business, I always pick up some bread from Sungsimdang.", source: "Day 068 교재2", meaning: meanings["pick up_3"] },
        { week: 14, ko: "고맙지만 괜찮아. 빵 먹으면 속이 더부룩해서. 빵은 뭔가 내 몸에 안 맞아.", en: "I’m good, thanks. I feel bloated when I have bread. There must be something about bread that just doesn’t agree with me.", source: "Day 068 교재2", meaning: null },
        { week: 14, ko: "야간 근무하면서 야식하는 나쁜 습관이 생긴 것 같아.", en: "It seems like I’ve picked up a bad habit of late-night snacking from working the night shift.", source: "Day 068 교재2", meaning: meanings["pick up_4"] },
        { week: 14, ko: "아! 그래서 지난 몇 주 동안 살이 찐 거구나. 근데 야식은 정말 몸에 안 좋아. 꼭 줄여야 해.", en: "Aha! That explains the extra pounds you’ve put on in the last few weeks. That’s totally unhealthy. You should definitely cut down.", source: "Day 068 교재2", meaning: null },
        { week: 14, ko: "여보, 숙모님이 우리 아파트 잘 찾아오실지 조금 걱정이네. 이번이 서울 첫 방문이잖아.", en: "Honey, I am a bit worried that your aunt won’t be able to find her way to our apartment. This is her first visit to Seoul, after all.", source: "Day 068 교재3", meaning: null },
        { week: 14, ko: "걱정 마. 내가 공항에 마중 나갈 거야. 그러면 숙모님이 지하철 타느라 헤매지 않으셔도 되니까.", en: "No worries. I’ll pick her up at the airport. That way, she doesn’t have to try and figure out the subway system.", source: "Day 068 교재3", meaning: meanings["pick up_2"] },
        { week: 14, ko: "그럼 너무 좋지. 그런데 오늘 밤에 줌 회의 있다고 그러지 않았어?", en: "That would be so nice. But didn’t you mention that you have a Zoom meeting tonight?", source: "Day 068 교재3", meaning: null },
        { week: 14, ko: "다행히 다음 주 월요일로 미뤄졌어.", en: "That has been pushed back to next Monday, thankfully.", source: "Day 068 교재3", meaning: null },
        { week: 14, ko: "너무 잘됐다! 그럼 당신이 (마중) 나간 동안 나는 마트에 들러서 장을 좀 볼게.", en: "Well, that turned out perfectly! I am going to swing by the store to pick up some groceries while you are out, then.", source: "Day 068 교재3", meaning: meanings["pick up_3"] },
        { week: 14, ko: "좋아! 우리가 집에 도착하면 9시쯤 될 것 같아.", en: "Sounds like a plan! I think it’ll be around 9 o’clock when we get home.", source: "Day 068 교재3", meaning: null },
        { week: 14, ko: "그녀는 정말 눈치가 없어.", en: "She seems terrible at taking hints.", source: "Day 069 교재1", meaning: null },
        { week: 14, ko: "금방 알아차리셨네요(= 눈치가 빠르시네요).", en: "You figured it out right away.", source: "Day 069 교재1", meaning: null },
        { week: 14, ko: "지금은 James를 귀찮게 안 할래. 아침에 James가 굉장히 예민했던 거 눈치 못 챘니?", en: "I wouldn’t bother James right now. Didn’t you pick up on how irritable he was this morning?", source: "Day 069 교재1", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "제 남편은 제가 아무리 눈치를 줘도 못 알아차립니다.", en: "My husband never picks up on any of my hints.", source: "Day 069 교재1", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "A: 밤새 뒤척였어. 한 숨도 못 잤어. (다음 날) 바쁜 날 직전이면 꼭 이래.", en: "A: I was tossing and turning all night. I couldn’t sleep at all. That always happens right before a busy day.", source: "Day 069 교재1", meaning: null },
        { week: 14, ko: "B: 정말? 난 전혀 몰랐네. 저녁 식사 자리에서 힘이 넘치고 사람들과도 잘 어울리고 해서 말이야.", en: "B: Really? I didn’t pick up on that at all. You seemed energetic and were mingling with everyone at dinner tonight.", source: "Day 069 교재1", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "민지는 생각보다 빠르게 언어의 뉘앙스를 알아차리더군요. 타고났어요!", en: "Minji picked up on the nuances of the language faster than expected. She’s a natural!", source: "Day 069 교재1", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "A: 다섯 살짜리 아들이 학교에서 욕을 하는 바람에 문제가 생겼어. 나한테 배운 게 확실해.", en: "A: My 5-year-old son got in trouble for swearing in school. He must’ve learned that from me.", source: "Day 069 교재1", meaning: null },
        { week: 14, ko: "B: 아들 있는 데서는 말 조심해야 해. 애들은 듣는 건 전부 흡수한단 말이야.", en: "B: Be careful what you say around him. Kids pick up on everything they hear.", source: "Day 069 교재1", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "그 둘 대화가 없는 것 눈치챘어? 헤어졌나 봐….", en: "Did you pick up on the lack of conversation between those two? It seems like they broke up…", source: "Day 069 교재2", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "정말 그렇게 생각해? 네가 그 말을 하니까 지난번에 Sarah랑 외출했을 때 커플 반지를 안 끼고 있었네. 야, 너 정말 이런 것에 눈치 빠르구나. 네가 말 안 했으면 난 전혀 몰랐을 거야.", en: "Do you really think so? Now that you mention it, I noticed Sarah wasn’t wearing her couple ring the last time we went out. Hey, you’re really good at picking up on stuff like that. I would have never guessed unless you said something.", source: "Day 069 교재2", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "Nicholas가 오늘 아침에 기분이 안 좋아 보이더라. 어젯밤에 무슨 일 있었나 싶기도 하네.", en: "Nicholas seemed to be in a bad mood this morning. I wonder if something happened last night.", source: "Day 069 교재2", meaning: null },
        { week: 14, ko: "진짜 그랬어? 난 모르겠던데. 한번 물어보지 그래?", en: "Did he really? I didn’t pick up on that. Why don’t we ask him?", source: "Day 069 교재2", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "그 술집 분위기 이상한 거 느꼈니?", en: "Did you pick up on the strange vibe in that pub?", source: "Day 069 교재2", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "그래! 아마 여자라고는 우리밖에 없어서 그런 걸 거야. 여자들은 잘 안 가는 곳이었던 것 같아. 내가 있을 곳이 아닌 느낌이었어.", en: "Yes! I think it was because we were the only girls there. I guess it was the kind of place that girls don’t usually go to. I felt like I didn’t belong there.", source: "Day 069 교재2", meaning: null },
        { week: 14, ko: "제게 (영어로의) 전화 통화가 어렵다고 호소하는 한국인 학생들이 있습니다.", en: "I’ve got some Korean students who complain to me about the difficulties of talking on the phone.", source: "Day 069 교재3", meaning: null },
        { week: 14, ko: "그들은 이렇게 말합니다. “영어로 전화 통화를 할 때면 상대방 말을 이해하기 어렵습니다.”", en: "They say, “I can barely understand what the other person is saying when we speak in English.”", source: "Day 069 교재3", meaning: null },
        { week: 14, ko: "이들이 왜 그런 말을 하는지 알겠어요.", en: "You know, I see where they’re coming from.", source: "Day 069 교재3", meaning: null },
        { week: 14, ko: "소통이라는 것이 그저 말로 하는 표현만은 아니니까요.", en: "Communication itself isn’t just about verbal expressions.", source: "Day 069 교재3", meaning: null },
        { week: 14, ko: "몸짓 언어와 표정도 중요한 부분입니다.", en: "Our body language and expressions are also a huge part.", source: "Day 069 교재3", meaning: null },
        { week: 14, ko: "그래서 저는 줌 수업 시 항상 학생들에게 카메라를 켜라고 합니다.", en: "So I always encourage my students to turn on their cameras during Zoom classes.", source: "Day 069 교재3", meaning: null },
        { week: 14, ko: "서로의 얼굴을 볼 수 있으면 수업 내용을 파악하기가 훨씬 더 쉬워집니다.", en: "It’s so much easier for them to pick up on what’s being communicated if we can see each other’s faces.", source: "Day 069 교재3", meaning: meanings["pick up on_1"] },
        { week: 14, ko: "반창고 떼는 건 진짜 아프다. 그래서 빨리 확 떼어 버린다.", en: "Pulling off bandages can be really painful, so I choose to rip them off quickly.", source: "Day 070 교재1", meaning: meanings["pull off_1"] },
        { week: 14, ko: "저녁을 거하게 먹고 나면 청바지 벗는 게 쉽지 않다.", en: "I have a hard time pulling my jeans off after a big dinner.", source: "Day 070 교재1", meaning: meanings["pull off_1"] },
        { week: 14, ko: "다른 사람들은 벙거지 모자를 쓰면 멋진 것 같은데, 나는 (벙거지 스타일을) 소화하기 어렵다.", en: "I think other people look cool in bucket hats, but I can’t pull it off.", source: "Day 070 교재1", meaning: meanings["pull off_2"] },
        { week: 14, ko: "A: 마감시간 맞추려면 24시간 이내에 책을 50페이지나 써야 해.", en: "A: I have 24 hours to write 50 pages before my book deadline.", source: "Day 070 교재1", meaning: null },
        { week: 14, ko: "B: 이런. 할 수 있겠어?", en: "B: Oh my. Do you think you can pull it off?", source: "Day 070 교재1", meaning: meanings["pull off_3"] },
        { week: 14, ko: "(저는) 아침에 엘리베이터에 탈 때 거울로 매무새를 확인하고 셔츠에 붙은 보푸라기나 고양이 털을 떼 냅니다.", en: "When I’m taking the elevator in the morning, I check myself out in the mirror and pull off any lint or cat hair on my shirt.", source: "Day 070 교재1", meaning: meanings["pull off_1"] },
        { week: 14, ko: "20대가 지나면 소화하기 어려운 20가지 스타일", en: "20 Looks That Are Really Hard to Pull Off Past Your Twenties", source: "Day 070 교재1", meaning: meanings["pull off_2"] },
        { week: 14, ko: "주연 배우가 아팠는데도 개막일 밤에 믿기 힘든 연기를 보여 주었다.", en: "The lead actor was sick, but he still pulled off an incredible performance on opening night.", source: "Day 070 교재1", meaning: meanings["pull off_3"] },
        { week: 14, ko: "아침에 등산을 다녀왔더니 발이 부은 것 같아. 신발이 안 벗겨져.", en: "I think my feet are swollen from this morning’s hike. It’s really hard to pull off my shoes.", source: "Day 070 교재2", meaning: meanings["pull off_1"] },
        { week: 14, ko: "응, 나도 등산 오래 하면 그럴 때가 있어. 도와줄까? 그나저나 등산은 어디로 갔던 거야?", en: "Yeah, that sometimes happens to me after a long hike. Do you need a hand? Where did you go hiking, by the way?", source: "Day 070 교재2", meaning: null },
        { week: 14, ko: "이 엄청난 틱톡 영상 좀 봐! 이 학생이 어떻게 이런 걸 할 수 있는지 믿기지 않아. 춤추는 모습이 거의 바닥 위를 떠다니네.", en: "Look at this amazing TikTok video! I can’t believe this student can even pull off something like this. The way he’s dancing, he’s basically floating over the floor.", source: "Day 070 교재2", meaning: meanings["pull off_3"] },
        { week: 14, ko: "응. 나 그 영상 봤어. 2억 뷰를 기록했고, ‘좋아요’도 230만 개가 달렸나 보더라.", en: "Oh, yeah. I’ve seen that video. Apparently, it’s gotten over 200 million views and 2.3 million likes on TikTok.", source: "Day 070 교재2", meaning: null },
        { week: 14, ko: "머리를 파란색 염색할까 고민 중인데, 내가 소화할 수 있을지 모르겠네. 나한테 어울릴까?", en: "I’ve been thinking about dyeing my hair blue, but I’m not sure I can pull it off. Do you think it would suit me?", source: "Day 070 교재2", meaning: meanings["pull off_2"] },
        { week: 14, ko: "무슨 생각을 하는 거야? 너 60대잖아. 네 나이 때 그런 말도 안 되는 색깔을 소화할 수 있는 사람은 없어.", en: "What are you thinking? You’re in your 60s. Nobody your age could pull off something that crazy.", source: "Day 070 교재2", meaning: meanings["pull off_2"] },
        { week: 14, ko: "나는 손흥민 선수가 뛰는 토트넘의 골수 팬이다.", en: "I am a big fan of Tottenham, the team that Son Heung-min plays for.", source: "Day 070 교재3", meaning: null },
        { week: 14, ko: "지난 주말에는 첼시와의 경기가 있었다.", en: "They had a match against Chelsea last weekend.", source: "Day 070 교재3", meaning: null },
        { week: 14, ko: "전반에 2점 차이로 지고 있었지만, 후반에 손흥민 선수가 해트 트릭을 성공했다.", en: "In the first half they were down by two goals, but Son pulled off a hat trick in the second half.", source: "Day 070 교재3", meaning: meanings["pull off_3"] },
        { week: 14, ko: "후반 75분까지 지고 있었는데 승리를 따냈다니 믿기지 않았다.", en: "It was unbelievable that they managed to pull off a victory when they were losing the game well into 75 minutes.", source: "Day 070 교재3", meaning: meanings["pull off_3"] },
        { week: 14, ko: "나는 현재 (해외) 온라인 MBA 과정을 이수 중이다.", en: "I am currently working on an online MBA.", source: "Day 070 교재3", meaning: null },
        { week: 14, ko: "원래는 리포트를 마쳐서 영국 시각으로 자정까지 제출해야만 했다.", en: "I was actually already supposed to have finished my paper and turned it in by midnight, British time.", source: "Day 070 교재3", meaning: null },
        { week: 14, ko: "근데 시차 때문에 2시간밖에 남지 않았다는 걸 몰랐다. 그래서 제때 제출하지 못했다.", en: "But with the time difference, I didn’t realize that I had only two hours left, and I couldn’t quite pull it off in time.", source: "Day 070 교재3", meaning: meanings["pull off_3"] },
        { week: 14, ko: "다행히 교수님께 말씀드렸더니 기한을 연장해 주셔서 벌칙 없이 리포트를 제출할 수 있었다.", en: "Thankfully, after I talked to my professor, he extended the deadline so I could submit the paper without penalty.", source: "Day 070 교재3", meaning: null },
        { week: 14, ko: "운이 좋았다. 하지만 앞으로는 같은 실수를 하지 않도록 조심해야 할 것 같다.", en: "I was lucky, but I’ll have to be careful not to make the same mistake in the future.", source: "Day 070 교재3", meaning: null },
        
        // Week 15
        { week: 15, ko: "사용하고 난 후에는 반드시 운동기구를 제자리에 두기 바랍니다. 그렇지 않으면 다른 체육관 회원들이 필요한 기구를 찾을 수가 없습니다.", en: "Please be sure to put away weights after you use them. Otherwise, other gym members can’t find what they need.", source: "Day 071 교재1", meaning: meanings["put away_1"] },
        { week: 15, ko: "저는 근근이 먹고살아서 공과금을 내고 나면 저축할 돈이 거의 남지 않아요.", en: "I live paycheck to paycheck. I don’t have any money left to put away after paying all my bills.", source: "Day 071 교재1", meaning: meanings["put away_2"] },
        { week: 15, ko: "이 먹방 유튜버는 혼자서 삼겹살 3인분을 해치우지. 그러고도 후식 먹을 배는 따로 있어.", en: "This mukbang YouTuber can put away three servings of pork belly by herself and still has room for dessert.", source: "Day 071 교재1", meaning: meanings["put away_3"] },
        { week: 15, ko: "제 아내는 뭐든 여기저기 두는 습관이 있어요. 절대로 제자리에 두지를 않지요.", en: "My wife has this habit of leaving everything scattered around, never putting things away.", source: "Day 071 교재1", meaning: meanings["put away_1"] },
        { week: 15, ko: "신형 아이패드를 사려고 그동안 돈을 모아 왔어. 그런데 그걸 보러 애플 매장에 갔더니 출시 이틀 만에 이미 다 팔렸더라.", en: "I’ve been putting away money for this new iPad, but when I went to the Apple Store to check one out, I found that they sold out just two days after launch.", source: "Day 071 교재1", meaning: meanings["put away_2"] },
        { week: 15, ko: "내 기억이 맞다면, 우리 삼촌은 혼자 소주 다섯 병을 마실 수 있었다.", en: "If I remember right, my uncle could put away five bottles of soju by himself.", source: "Day 071 교재1", meaning: meanings["put away_3"] },
        { week: 15, ko: "마르기 전에 재킷 (옷장에) 넣지 마! 그러니까 옷에 곰팡이가 피지.", en: "Don’t put away your jacket before it’s dry! That’s how you get moldy clothes.", source: "Day 071 교재2", meaning: meanings["put away_1"] },
        { week: 15, ko: "알았어, 알았어. 하룻밤 동안 건조대에 널어 둘게.", en: "Okay, okay. I’ll hang it up on the drying rack overnight.", source: "Day 071 교재2", meaning: null },
        { week: 15, ko: "내년 여름에 유럽 여행 갈 계획이라고 들었어. 난 절대 형편이 안 돼. 여행 경비를 어떻게 마련하니?", en: "I heard you’re planning a trip to Europe next summer. I could never afford that. How can you come up with the money?", source: "Day 071 교재2", meaning: null },
        { week: 15, ko: "매달 월급에서 조금씩 떼어서 여행 자금으로 모아 왔지. 이게 쌓이면 크거든!", en: "I’ve been putting away a little from each paycheck into a travel fund. It really adds up!", source: "Day 071 교재2", meaning: meanings["put away_2"] },
        { week: 15, ko: "뭘 먹어도 살이 진짜 안 쪄요. 아빠도 나랑 마찬가지잖아요. 그렇죠, 아빠?", en: "No matter what I eat, I just can’t seem to gain weight. I guess you have the same problem, right, Dad?", source: "Day 071 교재2", meaning: null },
        { week: 15, ko: "그래, 억지로라도 단백질을 충분히 섭취해야 하는데 우리는 안 그러잖아. 사촌 Robert를 봐. 닭고기랑 콩을 거의 매끼 엄청나게 먹잖아. 게다가 단백질 셰이크도 많이 먹고 말이지.", en: "Yes, but I think we’re just not forcing ourselves hard enough to eat protein. Look at your cousin Robert. He puts away a lot of chicken and beans almost every meal, and then he downs protein shakes on top of that.", source: "Day 071 교재2", meaning: meanings["put away_3"] },
        { week: 15, ko: "이 사무실로 이사 온 후에는 공간이 있는 곳에 되는대로 물건을 두고 있다.", en: "Ever since I moved into this place, I’ve been trying to put things away anywhere there’s space.", source: "Day 071 교재3", meaning: meanings["put away_1"] },
        { week: 15, ko: "사무실이 정말 엉망이 되었다.", en: "It’s become a disorganized mess.", source: "Day 071 교재3", meaning: null },
        { week: 15, ko: "그래서 이번 주말에 친구 트럭을 빌릴 예정이다.", en: "That’s why I’m planning on borrowing a friend’s truck this weekend.", source: "Day 071 교재3", meaning: null },
        { week: 15, ko: "저렴한 가구점에 가서는 옷장이랑 서랍을 살 것이다.", en: "I’m gonna go to that cheap furniture store and get some closets and drawers.", source: "Day 071 교재3", meaning: null },
        { week: 15, ko: "교재와 수업 자료를 둘 곳이 마련되면, 이 사무실이 다양한 목적으로 더 유용하게 사용할 수 있다.", en: "Once I have proper places to put away all my textbooks and teaching materials, this place can be more useful for all kinds of purposes.", source: "Day 071 교재3", meaning: meanings["put away_1"] },
        { week: 15, ko: "예를 들어, 케틀 벨을 사서 오전에 여기서 운동을 할 수도 있을 것이다.", en: "Like, I could even buy some kettle bells and do workouts here in the morning.", source: "Day 071 교재3", meaning: null },
        { week: 15, ko: "휴대폰 내려놓고 저녁 먹어야지!", en: "Put down your phone and eat your dinner!", source: "Day 072 교재1", meaning: meanings["put down_1"] },
        { week: 15, ko: "내가 볼 때 Alcon에서의 네 인턴 경력은 이력서에 기재하기에는 너무 짧아.", en: "I think your internship experience at Alcon is too short to put down on your resume.", source: "Day 072 교재1", meaning: meanings["put down_2"] },
        { week: 15, ko: "자전거를 대여하려면 담보로 신분증을 맡겨야 해.", en: "To rent a bike, you need to put down your ID as collateral.", source: "Day 072 교재1", meaning: meanings["put down_3"] },
        { week: 15, ko: "전 여자 친구랑 만날 때 항상 나를 무시한다는 느낌이 들었어. 늘 성공한 전 남자 친구와 나를 비교해서 내가 아무것도 아닌 것 같은 기분이 들게 했지.", en: "When I was dating my ex, I felt like she was always putting me down. She always compared me with her successful ex-boyfriend and made me feel like I was nothing.", source: "Day 072 교재1", meaning: meanings["put down_4"] },
        { week: 15, ko: "와인 잔을 너무 빨리 내려놓는 바람에 와인이 테이블에 쏟아졌다.", en: "I put down the wine glass too quickly and it spilled onto the table.", source: "Day 072 교재1", meaning: meanings["put down_1"] },
        { week: 15, ko: "저는 할 일이 너무 많을 때는 종이에 제 생각을 적으려고 합니다. 정리하는 데 도움이 됩니다.", en: "I try to put down my thoughts on paper when I have too many things to do. It helps me get organized.", source: "Day 072 교재1", meaning: meanings["put down_2"] },
        { week: 15, ko: "고객들이 차를 빌리려면 보증금으로 30만원을 예치해야 합니다.", en: "We require that our customers put down a 300,000 won security deposit to rent a car.", source: "Day 072 교재1", meaning: meanings["put down_3"] },
        { week: 15, ko: "그 술집에서 탭을 오픈하려면(= 나중에 술값을 한 번에 계산하려면) 카드를 맡겨야 해.", en: "If you want to open a tab at the bar, you need to put down your card.", source: "Day 072 교재1", meaning: meanings["put down_3"] },
        { week: 15, ko: "모든 사람들이 있는 데서 꼭 그렇게 나를 깎아내려야 했어?", en: "Why did you have to put me down in front of everybody like that?", source: "Day 072 교재1", meaning: meanings["put down_4"] },
        { week: 15, ko: "저녁 식사 자리에서 아빠가 엄마가 만든 음식을 깎아내리면 마음이 안 좋다. 특히 엄마가 정말 열심히 건강식을 준비했을 때는 더 그렇다.", en: "At the dinner table, it’s disheartening when Dad puts down Mom’s cooking, especially when she’s worked hard to prepare a healthy meal.", source: "Day 072 교재1", meaning: meanings["put down_4"] },
        { week: 15, ko: "우리 남편은 변기 시트를 내려놓으라고 아무리 말 해도 안 돼요. 정말 짜증 나네요.", en: "My husband can’t be bothered to put the toilet seat down, which is really frustrating.", source: "Day 072 교재2", meaning: meanings["put down_1"] },
        { week: 15, ko: "하하. 남자들이야 맨날 그렇죠. 그쪽 남편만이 아니에요. 저희 남편도 “깜박했다”, “오늘 좀 정신이 없다”라는 등 온갖 핑계를 대면서 늘 그러거든요. 그러니까 그런 걸로 신경 쓰지 마세요.", en: "Haha. Men are always like that. It’s not just your husband. My husband is always doing that, coming up with all these different excuses, like “It just slipped my mind,” or “I’m not myself today,” so don’t let it get to you.", source: "Day 072 교재2", meaning: null },
        { week: 15, ko: "이 스포츠카를 살까 싶은데, 가격이 부담스러운 게 문제야.", en: "I was thinking of getting this sports car. The thing is, I can barely afford it.", source: "Day 072 교재2", meaning: null },
        { week: 15, ko: "그럼 리스하는 건 어때? 신용만 괜찮으면 선수금 없이 새 차를 리스할 수 있을지도 모르거든.", en: "Then how about just leasing it? If you have good enough credit, you might even be able to lease a new car without putting anything down.", source: "Day 072 교재2", meaning: meanings["put down_3"] },
        { week: 15, ko: "지원서에 긴급 연락처를 기재하지 않으셨더군요. 이유가 있을까요?", en: "I noticed you didn’t list any emergency contact on your application form. Is there a reason for that?", source: "Day 072 교재2", meaning: meanings["put down_2"] },
        { week: 15, ko: "아, 누구를 기재해야 할지 결정을 못 해서요. 가족이 해외에 살거든요. 그래서 친한 친구를 추가할까 합니다. 확정하는 대로 바로 기재할게요.", en: "Oh, I’m still deciding who to put down. My family lives abroad, so I’m considering a close friend. I’ll fill it out as soon as I confirm it with them.", source: "Day 072 교재2", meaning: meanings["put down_2"] },
        { week: 15, ko: "지난 주말 어느 오래된 서점을 둘러보고 있다가 매력적인 이 책을 발견했는데 첫 페이지부터 매료되었다.", en: "I was checking out an old bookstore last weekend when I came across this charming book and I was hooked from the first page.", source: "Day 072 교재3", meaning: null },
        { week: 15, ko: "바닥 코너 쪽에 앉아서 읽었는데, 손에서 놓을 수가 없었다.", en: "I sat in the corner on the floor, reading it, completely unable to put it down.", source: "Day 072 교재3", meaning: meanings["put down_1"] },
        { week: 15, ko: "몇 시간을 (책을 읽으면서) 거기에 있다가 결국 구매했다.", en: "I was there for hours, and eventually bought it.", source: "Day 072 교재3", meaning: null },
        { week: 15, ko: "책이라는 것 때문에 이렇게 시간 가는 줄 모를 수 있다는 게 너무 좋다.", en: "I love how books can make me lose track of time like that.", source: "Day 072 교재3", meaning: null },
        { week: 15, ko: "오늘 밤에 고등학교 때 친구들이랑 파티에 갔는데, 아내도 데려갔다.", en: "I went to a party with my high school friends tonight and brought my wife along.", source: "Day 072 교재3", meaning: null },
        { week: 15, ko: "다 같이 좋은 시간을 보낼 것을 기대했다.", en: "I was hoping we’d have a good time together.", source: "Day 072 교재3", meaning: null },
        { week: 15, ko: "그런데 아내가 파티 중간에 내 고등학교 때 별명 때문에 나를 놀렸다.", en: "But at one point, she made fun of me for my old high school nickname.", source: "Day 072 교재3", meaning: null },
        { week: 15, ko: "내 별명은 ‘책벌레’였다. 그런데 아내는 내가 몇 년 동안 웹툰 말고는 읽은 것이 없다고 했다.", en: "I used to be called “Bookworm,” but she said I haven’t read anything besides webtoons in ages.", source: "Day 072 교재3", meaning: null },
        { week: 15, ko: "나를 무시하는 느낌이었다.", en: "It felt like she was putting me down.", source: "Day 072 교재3", meaning: meanings["put down_4"] },
        { week: 15, ko: "그 순간은 그냥 웃어넘겼지만 정말 기분이 상했다.", en: "I laughed it off in the moment, but it actually hurt.", source: "Day 072 교재3", meaning: null },
        { week: 15, ko: "그 이후로 저녁 내내 기분이 이전 같지 않았다.", en: "The rest of the evening just didn’t feel the same.", source: "Day 072 교재3", meaning: null },
        { week: 15, ko: "(내가) 몇 달째 미루고 있던 복잡한 세금 (신고) 서류 알지? 드디어 처리했어.", en: "You know that complicated tax paperwork I was putting off for months? I finally got around to it.", source: "Day 073 교재1", meaning: meanings["put off_1"] },
        { week: 15, ko: "남자 친구가 데이트 중에 자기 엄마한테 전화를 해서는 어느 카페에 가야 할지 묻더군요. 정말 정이 떨어지더라고요.", en: "He called his mom during our date to ask which cafe we should go to. It totally put me off.", source: "Day 073 교재1", meaning: meanings["put off_2"] },
        { week: 15, ko: "주문한 음식이 사진과 완전히 달랐는데 환불도 해주지 않아 정말 정이 떨어졌다(= 기분이 상했다).", en: "I was really put off after the dish I ordered was totally different from the photo and they wouldn’t refund me.", source: "Day 073 교재1", meaning: meanings["put off_2"] },
        { week: 15, ko: "이번 여름에 남미에 정말 가고 싶은데, 뉴스 보니까 최근에 위험한 모기 매개 바이러스가 유행한다고 하네. 그래서 남미 여행을 미루기로 했어.", en: "I really want to go to South America this summer, but the news is saying there’s a dangerous mosquito-borne virus going around these days, so I decided to put that trip off.", source: "Day 073 교재1", meaning: meanings["put off_1"] },
        { week: 15, ko: "담배 냄새가 너무 싫어서 흡연자와는 절대 사귀지 않아요.", en: "I would never date a smoker because the smell of tobacco really puts me off.", source: "Day 073 교재1", meaning: meanings["put off_2"] },
        { week: 15, ko: "나는 야구 광팬이다. 그런데 스타 선수들이 고액 계약을 맺을 때마다, 계약하기 전의 경기력에 미치지 못하더라. 우리 팀의 돈을 이렇게 낭비하는 걸 볼 때면 정말 야구에 대한 정이 떨어진다.", en: "I’m a big baseball fan, but I’ve noticed that whenever a star player secures a lucrative contract, his performance never lives up to his pre-contract performances. Seeing my team’s money wasted like that really puts me off.", source: "Day 073 교재1", meaning: meanings["put off_2"] },
        { week: 15, ko: "휴대폰으로 게임하는 거야? 너무 게으름 피우는 것 같군. 서류가 한 뭉치나 있던데, 그 일은 다 처리한 거야?", en: "You’re playing games on your phone? It looks like you’re slacking off. Did you ever get around to that work ‒ I mean, those piles of paperwork?", source: "Day 073 교재2", meaning: null },
        { week: 15, ko: "사실은 미뤄 왔던 일을 방금 다 끝냈거든. 이제 막 잠깐 쉬려고 하는 건데!", en: "I honestly did just get through all the stuff I’d been putting off. I was just starting to take a break!", source: "Day 073 교재2", meaning: meanings["put off_1"] },
        { week: 15, ko: "이제 소득 신고는 다 마친 거야? 이번 주까지 해야 해. 더 미루면 안 돼.", en: "Did you file your taxes yet? This week is the deadline. You can’t put it off any longer.", source: "Day 073 교재2", meaning: meanings["put off_1"] },
        { week: 15, ko: "알고 있으니까 그만 좀 말해! 작년처럼 그러지 않아. 올해는 회계사한테 세금 신고 맡겼어. 이미 다 했다고!", en: "Stop trying to make me feel bad! It’s not like last year. I actually got an accountant to take care of my taxes this year. They’re already done!", source: "Day 073 교재2", meaning: null },
        { week: 15, ko: "은지가 너무 우아해서 완전 반했었거든. 그런데 욕을 하는 걸 듣고는 정이 뚝 떨어졌어.", en: "I had a big crush on Eunji in part because I thought she was classy, so when I heard her swearing, that really put me off.", source: "Day 073 교재2", meaning: meanings["put off_2"] },
        { week: 15, ko: "우아해 보이기는 하지. 그런데 그거 알아? 욕만 하는 게 아니야. 거의 모든 사람들에 대해서 험담을 해. 내가 너라면 은지를 멀리할 거야.", en: "She seems classy, but you know what? It’s not just her swearing. She also gossips about almost everyone. I’d stay away from her if I were you.", source: "Day 073 교재2", meaning: null },
        { week: 15, ko: "앞서 말씀하신 것처럼, 분위기 반전을 위해서는 뭔가 조치가 필요합니다.", en: "As you mentioned earlier, something needs to be done to turn things around.", source: "Day 073 교재3", meaning: null },
        { week: 15, ko: "석 달연속 고객이 줄고 있고, 지난달은 1월 대비 매출이 30% 감소했습니다.", en: "We’ve been losing customers for three months straight, and our sales were down 30% last month from January.", source: "Day 073 교재3", meaning: null },
        { week: 15, ko: "큰 변화가 필요합니다.", en: "We’re in need of some big changes.", source: "Day 073 교재3", meaning: null },
        { week: 15, ko: "신규 고객을 유입해야 하고 기존 고객층도 유지해야 합니다.", en: "We need to bring in new customers while maintaining our existing customer base.", source: "Day 073 교재3", meaning: null },
        { week: 15, ko: "1층을 카페 공간으로 바꾸는 건 재미있는 생각이지만 충성 고객들을 실망시킬 수도있습니다.", en: "While turning the ground floor into a cafeteria is an interesting idea I’m afraid it may put off our loyal customers.", source: "Day 073 교재3", meaning: meanings["put off_2"] },
        { week: 15, ko: "어쨌든, 그 안건은 잠시 보류하고 머리를 맞대어 매출 신장을 위한 다른 방안을 고민해 봅시다.", en: "Anyway, let’s hold off on that for now and put our heads together to try to figure out other ways to boost sales.", source: "Day 073 교재3", meaning: null },
        { week: 15, ko: "A: 오늘 머리가 엉망이야. 밖에 나가기 싫어.", en: "A: My hair looks bad today. I don’t want to go outside.", source: "Day 074 교재1", meaning: null },
        { week: 15, ko: "B: 왜 이래! 그냥 모자 쓰고 가자.", en: "B: C’mon! Just put on a hat and let’s go.", source: "Day 074 교재1", meaning: meanings["put on_1"] },
        { week: 15, ko: "A: 머리가 아파….", en: "A: I have a headache...", source: "Day 074 교재1", meaning: null },
        { week: 15, ko: "B: 클래식 음악 좀 틀어 줄까?", en: "B: Do you want me to put on some classical music?", source: "Day 074 교재1", meaning: null },
        { week: 15, ko: "A: 이봐, Dave, 운동화는 왜 신고 있는 거야?", en: "A: Hey, Dave, why do you have on your running shoes?", source: "Day 074 교재1", meaning: meanings["have on_1"] },
        { week: 15, ko: "B: 퇴근하고 바로 조깅하러 가려고.", en: "B: I’m going for a jog straight after work.", source: "Day 074 교재1", meaning: null },
        { week: 15, ko: "A: 여보, 왜 옷이 침대에 널브러져 있는 거야?", en: "A: Honey, why is your wardrobe laying all over the bed?", source: "Day 074 교재1", meaning: null },
        { week: 15, ko: "B: 출근 첫날 입을 옷을 여러 벌 입어 보고 있었거든.", en: "B: I was trying on different outfits for my first day at work.", source: "Day 074 교재1", meaning: meanings["try on_1"] },
        { week: 15, ko: "식당에 들어가기 전에 바지 입으렴. 수영복 입고 들어가면 안 돼.", en: "Put on some pants before you go in the restaurant. You can’t wear your swimsuit in there.", source: "Day 074 교재1", meaning: meanings["put on_1"] },
        { week: 15, ko: "아침에 향수를 뿌리다가 욕실 바닥에 병을 떨어뜨렸어요.", en: "I was putting on my perfume this morning and dropped the bottle on my bathroom floor.", source: "Day 074 교재1", meaning: meanings["put on_1"] },
        { week: 15, ko: "스웨터를 두 개 나 입고 있는데도 얼어 죽겠다.", en: "Even though I have two sweaters on, I am still freezing.", source: "Day 074 교재1", meaning: meanings["have on_1"] },
        { week: 15, ko: "양말을 안 신었네? 발이 안 추워?", en: "You don’t have any socks on? Aren’t your feet cold?", source: "Day 074 교재1", meaning: meanings["have on_1"] },
        { week: 15, ko: "탈의실이 어디 있나요? 결정하기 전에 입어 보려고요.", en: "Where are the fitting rooms? I want to try this on before I decide.", source: "Day 074 교재1", meaning: meanings["try on_1"] },
        { week: 15, ko: "항상 먼저 입어 보고 구매하는 것이 좋습니다.", en: "It’s always a good idea to try something on before you buy it.", source: "Day 074 교재1", meaning: meanings["try on_1"] },
        { week: 15, ko: "Mary, 얼굴이 너무 빨개!", en: "Mary, your face is so red!", source: "Day 074 교재2", meaning: null },
        { week: 15, ko: "알아. 어제 공원에서 선크림 바르는 걸 깜박했거든.", en: "I know. I forgot to put on sunscreen at the park yesterday.", source: "Day 074 교재2", meaning: meanings["put on_1"] },
        { week: 15, ko: "그 재킷 입고 따뜻하겠어? 좀 얇게 보이는데.", en: "Are you going to be warm enough in that jacket? It looks pretty thin.", source: "Day 074 교재2", meaning: null },
        { week: 15, ko: "응. 방한용 내의를 두 겹이나 입고 있어. 그래서 괜찮을 거야. 걱정하지 마.", en: "Yeah. I have two layers of thermal underwear on, so I’ll be fine. Don’t worry.", source: "Day 074 교재2", meaning: meanings["have on_1"] },
        { week: 15, ko: "이번 주말에 파란색 셔츠를 봤는데, 옷걸이에 걸려 있을 때는 엄청 좋아 보였어. 그런데 입어 보니 나랑은 안 맞더라.", en: "I saw a blue shirt this weekend that looked great on the rack, but after trying it on, it definitely wasn’t for me.", source: "Day 074 교재2", meaning: meanings["try on_1"] },
        { week: 15, ko: "넌 그냥 검은색이 아닌 옷을 입는 게 두려울 뿐이야. 분명 잘 어울렸을 텐데.", en: "You are just afraid to wear any clothes that aren’t black. I’m sure you looked good.", source: "Day 074 교재2", meaning: null },
        { week: 15, ko: "자, 여러분, 이것은 체중을 불리고 싶은 분들에게 드리는 말씀입니다.", en: "Okay, everyone, this is for anyone hoping to gain a few pounds.", source: "Day 074 교재3", meaning: null },
        { week: 15, ko: "진짜로 살을 찌우고 싶다면 칼로리가 높은 음식을 섭취하는 것이 가장 중요합니다.", en: "If you’re serious about putting on weight, the most important thing to do is eat foods that are high in calories.", source: "Day 074 교재3", meaning: meanings["put on_1"] },
        { week: 15, ko: "일부 단백질 셰이크는 체중을 늘리기 위한 분들에게 특화되어 있으니 이런 걸 추천합니다.", en: "Some protein shakes are specifically made for people looking to gain weight ‒ I recommend those!", source: "Day 074 교재3", meaning: null },
        { week: 15, ko: "주기적으로만 먹는다면 살찌는 데 도움이 되는 단백질 바도 있습니다.", en: "There are also some protein bars that will help you put on weight if you eat them regularly.", source: "Day 074 교재3", meaning: meanings["put on_1"] },
        { week: 15, ko: "매일 섭취하는 칼로리를 잘 계산하는 것도 또 다른 방법입니다.", en: "Another thing is to keep track of the calories that you are consuming each day.", source: "Day 074 교재3", meaning: null },
        { week: 15, ko: "기록을 하면 원하는 만큼의 결과가 나타나지 않을 때 도움이 될 것입니다.", en: "Having a record is going to help you if you’re not seeing enough results.", source: "Day 074 교재3", meaning: null },
        { week: 15, ko: "체중 증가를 위한 여러분의 여정에 행운이 있기를 바랍니다!", en: "Good luck to you guys on your weight gaining journey!", source: "Day 074 교재3", meaning: null },
        { week: 15, ko: "어릴 때 엄마 꽃병을 깨뜨린 적이 있다. 엄마가 집에 오기 전에 부서진 조각을 붙이려 안간힘을 썼다.", en: "I broke my mom’s vase when I was young. I tried so hard to put together the shattered pieces before she came home.", source: "Day 075 교재1", meaning: meanings["put together_1"] },
        { week: 15, ko: "제 아내는 늘 냉장고에 있는 남은 음식으로 멋진 요리를 만들어냅니다.", en: "My wife always manages to put together amazing meals with leftovers in the fridge.", source: "Day 075 교재1", meaning: meanings["put together_2"] },
        { week: 15, ko: "자, 머리를 맞대어서 올여름 재미있는 여행 계획을 짜 보자.", en: "Let’s put our heads together and plan a fun trip this summer.", source: "Day 075 교재1", meaning: meanings["put together_2"] },
        { week: 15, ko: "조립 비용을 내고 싶지 않아서 새로 산 캐비닛을 직접 조립했다.", en: "I didn’t want to pay an assembly fee, so I put together my new cabinet myself.", source: "Day 075 교재1", meaning: meanings["put together_1"] },
        { week: 15, ko: "저는 드릴이 필요한 건 직접 조립할 수 없어요.", en: "I can’t put together anything that requires a drill.", source: "Day 075 교재1", meaning: meanings["put together_1"] },
        { week: 15, ko: "네가 앞부분 슬라이드 만들면 내가 마지막 부분 만들게. 그리고 이번 주말에 모두 합치자.", en: "You make the beginning slides, I’ll make the ending slides, and let’s put them all together this weekend.", source: "Day 075 교재1", meaning: meanings["put together_2"] },
        { week: 15, ko: "내 괴물 의상을 거의 다 완성했어. 이제 여기에 맞는 신발만 있으면 돼.", en: "I’ve almost finished putting together my monster costume. I just need some appropriate shoes.", source: "Day 075 교재1", meaning: meanings["put together_2"] },
        { week: 15, ko: "매년 파리를 찾는 관광객 수가 로마, 아테네, 베를린을 합친 것보다 더 많다.", en: "The number of tourists visiting Paris annually is more than those visiting Rome, Athens, and Berlin put together.", source: "Day 075 교재1", meaning: meanings["put together_3"] },
        { week: 15, ko: "이번 신규 스마트폰 모델의 첫 주 판매치가 이전 모델을 다 합친 것보다 더 많았다.", en: "The sales of this new smartphone model in its first week exceeded those of all previous models put together.", source: "Day 075 교재1", meaning: meanings["put together_3"] },
        { week: 15, ko: "내 휴대폰 스피커가 고장 났어. 고치려고 분해했는데 조립하는 방법을 모르겠어.", en: "The speaker on my phone stopped working. I took it apart to try and fix it, but now I don’t know how to put it back together.", source: "Day 075 교재2", meaning: meanings["put together_1"] },
        { week: 15, ko: "우와, 직접 했다고? 엄청 번거로웠을 텐데. 나라면 그냥 수리점으로 가져갔을 텐데.", en: "Wow, you tried to do it yourself? That must’ve been such a hassle. I would’ve just taken it to a repair shop.", source: "Day 075 교재2", meaning: null },
        { week: 15, ko: "왔니, 수진아. 좀 피곤해 보인다. 오늘 학교에서 힘들었어?", en: "Hi, Sujin. You look tired. Tough day at school?", source: "Day 075 교재2", meaning: null },
        { week: 15, ko: "네, 선생님이 저와 Hailey를 같은 그룹 프로젝트에 넣었거든요. 누가 뭘 할 건지를 두고 또 싸웠어요. 정말 힘들었어요!", en: "Yeah, the teacher put me together with Hailey for a project, and we fought again about who should do what. It was really draining!", source: "Day 075 교재2", meaning: meanings["put together_2"] },
        { week: 15, ko: "퇴근하면 늘 너무 피곤하다고 하네. 뭐 때문에 그렇게 바쁜 거야?", en: "You always say you’re exhausted after work. What’s keeping you so busy?", source: "Day 075 교재2", meaning: null },
        { week: 15, ko: "내년 예산안을 짜고 있거든. 예산안 만드는 건 원래 Jeff 일인데 육아 휴직 중이라 내가 인수인계를 받아야 했어.", en: "I’ve been putting together a budget plan for next year. It actually used to be Jeff’s job, but he’s on paternity leave, so I had to take over.", source: "Day 075 교재2", meaning: meanings["put together_2"] },
        { week: 15, ko: "오늘 낮에 망원동에 있는 샐러드 전문점에 점심을 먹으러 다녀왔다.", en: "I went to this salad place for lunch in Mangwon-dong this afternoon.", source: "Day 075 교재3", meaning: null },
        { week: 15, ko: "내 친구 Sam이 추천해 준 곳이었다.", en: "It was actually a place my friend, Sam recommended.", source: "Day 075 교재3", meaning: null },
        { week: 15, ko: "평일치고는 사람이 꽤 많아서 놀랐다.", en: "Surprisingly, it was pretty packed for a weekday.", source: "Day 075 교재3", meaning: null },
        { week: 15, ko: "근데 샐러드 전문점은 처음이라 주문을 어떻게 해야 할지 몰랐다.", en: "It was my first time at a salad place, though, so I couldn’t figure out how to order.", source: "Day 075 교재3", meaning: null },
        { week: 15, ko: "알고 보니 원하는 재료를 골라서 그릇에 한꺼번에 담으면 되는 거였다.", en: "It turned out you could just choose whatever ingredients you wanted and put them together in the bowl.", source: "Day 075 교재3", meaning: meanings["put together_2"] },
        { week: 15, ko: "원하는 것을 다 고르면 계산원이 무게를 재서 가격을 결정하게 된다.", en: "When you have everything you want, the cashier weighs it to figure out the price.", source: "Day 075 교재3", meaning: null },
        { week: 15, ko: "내 학생 중에는 교수님이 있다.", en: "I have a student who is a professor.", source: "Day 075 교재3", meaning: null },
        { week: 15, ko: "이 분은 반을 조별로 나눌 때 최대한 여러 인종이 한 조가 되게 하려고 한다고 했다.", en: "She told me that when she breaks up the class into small groups, she tries to make them diverse.", source: "Day 075 교재3", meaning: null },
        { week: 15, ko: "미국인 학생은 미국인끼리 한 조에, 중국인 학생은 중국인끼리 또 한 조에 편성하는 걸 원하지 않는다.", en: "She doesn’t want to put all the American students together in one group and all the Chinese students together in another.", source: "Day 075 교재3", meaning: meanings["put together_2"] },
        { week: 15, ko: "여러 배경의 학생들을 한 조에 편성한다.", en: "She puts students from various backgrounds together in each group.", source: "Day 075 교재3", meaning: meanings["put together_2"] },

        // Week 16
        { week: 16, ko: "나 방금 우리 (콘서트) 포스터 붙일 멋진 곳을 찾았어! 나 따라와 봐.", en: "I just found a great place to put up our posters! Come with me.", source: "Day 076 교재1", meaning: meanings["put up_1"] },
        { week: 16, ko: "나가기 전에 이 인테리어 사진들을 인스타에 올리자.", en: "Let’s put up these pictures of the decor on Instagram before we head out.", source: "Day 076 교재1", meaning: meanings["put up_3"] },
        { week: 16, ko: "보니까 시내에 신축 고층 건물을 올리는 모양이야. 다음 주에 공사 시작한대.", en: "Apparently, they will be putting up a new skyscraper downtown. I heard they’ll start construction next week.", source: "Day 076 교재1", meaning: meanings["put up_2"] },
        { week: 16, ko: "사촌이 (나를) 몇 주간 재워 주고는 있어. 이제는 다른 지낼 곳을 찾아야 해.", en: "My cousin has been putting me up for a few weeks. It’s time to find somewhere else to stay.", source: "Day 076 교재1", meaning: meanings["put up_4"] },
        { week: 16, ko: "(애완견을 잃어버린) 내 친구가 잃어버린 개를 찾기 위해 도시 곳곳에 전단지를 붙였다.", en: "My friend put up flyers all over the city to try and find her missing dog.", source: "Day 076 교재1", meaning: meanings["put up_1"] },
        { week: 16, ko: "그 카페가 최근에 빈티지 포스터를 붙였는데, 이 때문에 아늑하면서도 복고풍 감성이 더해졌다.", en: "The café recently put up vintage posters, giving it a cozy, retro vibe.", source: "Day 076 교재1", meaning: meanings["put up_1"] },
        { week: 16, ko: "이웃집 개들이 들어오지 못하도록 정원에 울타리를 칠까 해요.", en: "We were thinking of putting up a fence around our garden to keep out the neighbors’ dogs.", source: "Day 076 교재1", meaning: meanings["put up_2"] },
        { week: 16, ko: "보니까 박물관 있던 자리에 호텔을 지을 계획인가 봐요.", en: "Apparently, they’re planning to put up a hotel where the museum used to be.", source: "Day 076 교재1", meaning: meanings["put up_2"] },
        { week: 16, ko: "제 블로그에 숨이 막힐 정도로 멋진 일몰 사진을 올렸더니 바로 관심이 쏟아졌어요.", en: "I put up a breathtaking sunset photo on my blog, and it immediately got a lot of attention.", source: "Day 076 교재1", meaning: meanings["put up_3"] },
        { week: 16, ko: "저희 아파트를 리모델링하는 동안 Jeff가 몇 주간 재워 줬답니다.", en: "When my apartment was being renovated, Jeff put me up for a few weeks.", source: "Day 076 교재1", meaning: meanings["put up_4"] },
        { week: 16, ko: "이 반지 사진 찍어서 인스타에 올려도 될까?", en: "Can I take a picture of this ring and put it up on Instagram?", source: "Day 076 교재2", meaning: meanings["put up_3"] },
        { week: 16, ko: "제발 그러지 마! 이건 내가 직접 한 디자인이잖아. 네 계정에 올리면 어떡해. (내가 디자인한 건데) 그렇게 하면 마치 네가 한 것처럼 보일 것 아냐.", en: "Please don’t! This is my personal design. You can’t put it up on your account. It’ll look like you’re taking credit for it.", source: "Day 076 교재2", meaning: meanings["put up_3"] },
        { week: 16, ko: "뭐 때문에 소음이 이리 심한 거야? (이런 지) 벌써 한참 됐어.", en: "What’s all that noise? It’s been going on for a while.", source: "Day 076 교재2", meaning: null },
        { week: 16, ko: "저 아래쪽에 아파트 신축 공사를 하고 있어. 앞으로 몇 달 더 공사가 계속될 거야.", en: "They’re putting up a new apartment complex a few streets down. They’ll be working on it for the next few months.", source: "Day 076 교재2", meaning: meanings["put up_2"] },
        { week: 16, ko: "포스터 붙이는 것 좀 도와줄래? (우리가) 몇 주 있다가 카부츠 세일을 할 거라서.", en: "Hey, will you help me put up some of these posters? We’re going to have a car boot sale in a few weeks.", source: "Day 076 교재2", meaning: meanings["put up_1"] },
        { week: 16, ko: "포스터라고? 그거 효과 없을 텐데. 요즘 누가 포스터에 적힌 걸 보냐. 소문을 내려면 SNS에 올려야지.", en: "Posters? That’s not going to work. No one pays attention to what’s written on posters anymore. If you want to spread the word, you need to post it on social media.", source: "Day 076 교재2", meaning: null },
        { week: 16, ko: "음, 문제가 좀 생겼다.", en: "Well, I have a bit of a problem.", source: "Day 076 교재3", meaning: null },
        { week: 16, ko: "남동생이 최근에 안 좋게 이혼을 했는데, 내가 몇 주째 동생을 우리 집에 재워 주고 있다.", en: "My brother recently got out of a bad divorce, so I’ve been putting him up for the last few weeks.", source: "Day 076 교재3", meaning: meanings["put up_4"] },
        { week: 16, ko: "동생이 힘든 시간을 보내고 있어서 힘이 되어 주려고 한다.", en: "He’s been having a hard time, and I want to give him the support he needs.", source: "Day 076 교재3", meaning: null },
        { week: 16, ko: "우리 애들도 다들 삼촌을 도우려고 노력 중이다.", en: "All of my kids have been trying to help him out.", source: "Day 076 교재3", meaning: null },
        { week: 16, ko: "그런데 문제는, 그가 너무 오래 머물기 시작했다는 거다.", en: "But, here’s the thing, he’s starting to outstay his welcome.", source: "Day 076 교재3", meaning: null },
        { week: 16, ko: "동생이 소파에 앉아서 하루 종일 TV만 보면서 먹기만 한다.", en: "All he does is sit on the couch all day watching TV and eating our food.", source: "Day 076 교재3", meaning: null },
        { week: 16, ko: "동생 때문에 식비가 두 배나 늘었다.", en: "We’ve gone through twice as many groceries because of him.", source: "Day 076 교재3", meaning: null },
        { week: 16, ko: "식비를 좀 보태겠다는 말도없다. 심지어 집안일도 도와주지 않는다.", en: "He hasn’t offered to help out with the grocery bill, or even pitch in with chores around the house.", source: "Day 076 교재3", meaning: null },
        { week: 16, ko: "계속 이러면 얼마를 더 참으며 데리고 있을 수 있을지 모르겠다.", en: "If this keeps up, I don’t know how much longer we’ll be able to stand putting him up.", source: "Day 076 교재3", meaning: meanings["put up_4"] },
        { week: 16, ko: "미네소타에서 몇 년을 살고 나서, 더는 겨울을 견디기 힘들다고 판단하고 플로리다로 이사했습니다.", en: "After years of living in Minnesota, I decided I couldn’t put up with the winters anymore, and moved to Florida.", source: "Day 077 교재1", meaning: meanings["put up with_1"] },
        { week: 16, ko: "제 일이 너무 좋지만, 매일 2시간씩 걸리는 출퇴근을 언제까지 견딜 수 있을지 모르겠어요.", en: "I love my job, but I don’t know how long I can put up with this two-hour commute every day.", source: "Day 077 교재1", meaning: meanings["put up with_1"] },
        { week: 16, ko: "계란 프라이도 못 한다고? (그럼) 네 아내가 너를 어떻게 참지?", en: "You can’t fry an egg? How does your wife put up with you?", source: "Day 077 교재1", meaning: meanings["put up with_2"] },
        { week: 16, ko: "저는 비행기 타는 걸 너무 싫어하고, 아내는 차 타고 오래 여행하는 걸 못 견딥니다. 그래서 그냥 집에서 휴가를 즐겨야 할 것 같네요.", en: "I hate flying, and my wife can’t put up with long road trips. Staycation it is, I guess.", source: "Day 077 교재1", meaning: meanings["put up with_1"] },
        { week: 16, ko: "이 회사는 일하기 정말 좋은 곳이에요. 하지만 마감 시간을 못 지키는 건 용납하지 않습니다. 꼭 제시간에 업무한 걸 제출하셔야 해요.", en: "This company is a great place to work, but they don’t put up with missed deadlines. Make sure to submit your work on time.", source: "Day 077 교재1", meaning: meanings["put up with_1"] },
        { week: 16, ko: "제가 십 대 때 부모님이 저를 어떻게 참아 주셨는지 모르겠어요. 정말 문제아였거든요.", en: "I don’t know how my parents put up with me during my teenage years. I was a handful.", source: "Day 077 교재1", meaning: meanings["put up with_2"] },
        { week: 16, ko: "가끔씩 저를 참기 힘들다는 점은 인정합니다. 우리 팀에게 많은 것을 요구하지만, 그건 우리 모두가 최선을 다하기를 원하기 때문이에요.", en: "I admit that I’m hard to put up with at times. I demand a lot from my team, but it’s because I want us all to do our best.", source: "Day 077 교재1", meaning: meanings["put up with_2"] },
        { week: 16, ko: "자기야, 이거 세일하네! 돈 아끼려면 두 개 사야겠다.", en: "Oh, Babe, it’s on sale! We should get two to save money.", source: "Day 077 교재2", meaning: null },
        { week: 16, ko: "우리 예산으로는 당신의 낭비 습관을 감당하기 힘드네. 그리고 난 당신의 어린아이같은 모습을 참기 힘들어.", en: "Our budget can’t put up with your lavish spending, and I can’t put up with your childish logic.", source: "Day 077 교재2", meaning: meanings["put up with_2"] },
        { week: 16, ko: "저희도 이사 가기는 싫습니다. 그렇지만 윗집 소음을 더는 참기 힘들어요. 임대 계약을 취소해야 할 것 같습니다.", en: "We don’t want to move, but we can’t put up with the noise coming from the upstairs neighbor any longer. We need to cancel our lease.", source: "Day 077 교재2", meaning: meanings["put up with_1"] },
        { week: 16, ko: "이해합니다만, 그 집에 다시 이야기해 볼게요. 필요하다면 내보내겠습니다.", en: "I understand, but let me just talk to that neighbor again. I’ll remove him if I need to.", source: "Day 077 교재2", meaning: null },
        { week: 16, ko: "(네) 여자 친구가 문자를 확인하는 데 3일이 걸린다.... 어떻게 참니?", en: "It takes her three days to check your text messages… How do you put up with her?", source: "Day 077 교재2", meaning: meanings["put up with_2"] },
        { week: 16, ko: "여자 친구가 나를 많이 아끼기는 해. 그냥 이 친구 소통 방식이 그래.", en: "I know she really cares about me. That’s just the way she communicates.", source: "Day 077 교재2", meaning: null },
        { week: 16, ko: "룸메이트인 Steve를 만나기 전까지는 나는 늘 인내심이 많은 사람이었다.", en: "I had always been a patient person until I met my roommate, Steve.", source: "Day 077 교재3", meaning: null },
        { week: 16, ko: "설거지를 안 한 그릇을 며칠이나 싱크대에 두지를 않나, 밤늦게 음악을 크게 틀지를 않나, Steve 이 친구는 자신이 너무 형편없는 룸메이트라는 걸 전혀 몰랐다.", en: "From leaving dirty dishes in the sink for days to blasting music late at night, Steve had no idea of how terrible a roommate he was.", source: "Day 077 교재3", meaning: null },
        { week: 16, ko: "처음 몇 번은 이런 행동을 참으려고 했다.", en: "I tried to put up with his behavior the first couple of times.", source: "Day 077 교재3", meaning: meanings["put up with_2"] },
        { week: 16, ko: "하지만 시간이 가면서 인내심이 바닥이 나기 시작했다.", en: "However, as time went on, I started to lose my cool.", source: "Day 077 교재3", meaning: null },
        { week: 16, ko: "몇 번은 대놓고 따졌다. 하지만 아무것도 변하지 않았다.", en: "I confronted him several times, but nothing seemed to change.", source: "Day 077 교재3", meaning: null },
        { week: 16, ko: "평일 밤에 파티를 하겠다고 했을 때, 나는 결국 한계에 달했다.", en: "Finally, I reached my breaking point when he decided to host a party on a week night.", source: "Day 077 교재3", meaning: null },
        { week: 16, ko: "더는 이런 예의 없는 행동을 참을 수 없었다.", en: "I could no longer put up with such disrespect.", source: "Day 077 교재3", meaning: meanings["put up with_2"] },
        { week: 16, ko: "새로운 룸메이트를 찾아야 할 시점이라고 판단했다.", en: "I decided it was time to find a new roommate.", source: "Day 077 교재3", meaning: null },
        { week: 16, ko: "구인 공고에 문제가 좀 생겼어요. 진행하기 전에 의견을 구해야 할 것 같아서요.", en: "I’ve run into some trouble advertising your job posting. I’ll have to get your input before proceeding.", source: "Day 078 교재1", meaning: meanings["run into_3"] },
        { week: 16, ko: "휴대폰을 보다가 결국 회전문에 부딪히고 말았어요.", en: "I was staring at my phone and ended up running into the revolving door.", source: "Day 078 교재1", meaning: meanings["run into_1"] },
        { week: 16, ko: "여기서 보다니 반갑다! 조만간 커피 한잔해야지!", en: "Nice running into you! We should grab a coffee soon!", source: "Day 078 교재1", meaning: meanings["run into_2"] },
        { week: 16, ko: "착륙 직전에 난기류를 만났습니다.", en: "We ran into some turbulence just before landing.", source: "Day 078 교재1", meaning: meanings["run into_3"] },
        { week: 16, ko: "큰 문제만 없으면, 다음 달에 새 집에 들어갈 수 있을 거야.", en: "As long as we don’t run into any major issues, we should be able to move into our new house next month.", source: "Day 078 교재1", meaning: meanings["run into_3"] },
        { week: 16, ko: "Sally, 민수 보게 되면 문 앞에 택배 도착했다고 전해 줘.", en: "Sally, if you run into Minsu, tell him he has a package waiting at the entrance.", source: "Day 078 교재2", meaning: meanings["run into_2"] },
        { week: 16, ko: "알겠어! 민수 말이 나왔으니 말인데, 이번 주 내내 안 보이더라. 어디 갔지…? 아, 완전히 잊고 있었네! 내 정신 좀 봐. 지난주에 브리즈번으로 여행 갔지!", en: "Sounds good! Speaking of Minsu, I haven’t seen him all week. Where did he…? Oh, I totally forgot! I must be losing my mind. He went on a trip to Brisbane last week!", source: "Day 078 교재2", meaning: null },
        { week: 16, ko: "안녕하세요. 삼성페이에 문제가 생겼는데 좀 도와주실 수 있을까 해서요. 삼성페이로 강좌 등록을 시도하는데 이런 문제가 생겼습니다.", en: "Hello! There’s an error with my Samsung Pay, and I was hoping you could help me out with it. I ran into this problem while trying to sign up for the course using that app.", source: "Day 078 교재2", meaning: meanings["run into_3"] },
        { week: 16, ko: "불편을 드려 죄송합니다. 이런 일은 처음이네요. 한 시간 내로 다시 전화 드려도 될까요?", en: "Sorry for the inconvenience. We haven’t seen anything like this before. Do you mind if we get back to you in an hour or so?", source: "Day 078 교재2", meaning: null },
        { week: 16, ko: "John, 내가 이야기한 파일 구글 독스에서 볼 수 있어요. 내일까지 꼭 마무리 부탁해요. 문제 있으면 편하게 알려 주고요.", en: "John, you can access the file I mentioned in our Google Docs. Make sure to have it finished by tomorrow. Feel free to let me know if you run into any problems.", source: "Day 078 교재2", meaning: meanings["run into_3"] },
        { week: 16, ko: "바로 시작하겠습니다, 팀장님. 이사회 회의에 맞춰서 마무리하겠습니다.", en: "I’ll get right on it, sir. I will have it taken care of in time for the board meeting.", source: "Day 078 교재2", meaning: null },
        { week: 16, ko: "겨우 작동만 되는 세탁기를 몇 년간 쓴 후에 드디어 최신 기능이 탑재된 LG 신형세탁기를 장만했다.", en: "After years of using a washing machine that barely works, I finally got a brand new LG washing machine with all the latest features.", source: "Day 078 교재3", meaning: null },
        { week: 16, ko: "세탁기를 장만한 게 너무 신나서 배송을 기다리기가 힘들었다.", en: "I was so excited to get my hands on it that I could hardly wait for it to be delivered.", source: "Day 078 교재3", meaning: null },
        { week: 16, ko: "그런데 오늘 아침에 배송이 되었을 때 설치 기사분들이 예상치 못한 문제에 부딪혔다.", en: "But then, when it finally came this morning, the guys installing it ran into a problem.", source: "Day 078 교재3", meaning: meanings["run into_3"] },
        { week: 16, ko: "너무 커서 우리 집 작은 세탁실에 안 들어갔다.", en: "It was too big to fit into our little laundry room.", source: "Day 078 교재3", meaning: null },
        { week: 16, ko: "미리 공간을 쟀어야 했다.", en: "I guess we should have measured the space beforehand.", source: "Day 078 교재3", meaning: null },
        { week: 16, ko: "좋다 말았다.", en: "I feel like I got excited for nothing.", source: "Day 078 교재3", meaning: null },
        { week: 16, ko: "결국 매장에 다시 가서 우리 집 세탁실에 맞는 기본형을 골라야 할 것 같다.", en: "I think I’ll have to go back to the store and pick out a more basic model that will fit the space we have.", source: "Day 078 교재3", meaning: null },
        { week: 16, ko: "A: 앱솔루트 있나요?", en: "A: Do you have Absolute?", source: "Day 079 교재1", meaning: null },
        { week: 16, ko: "B: 아니요. 스미노프랑 스카이가 있습니다.", en: "B: No. We have Smirnoff and Sky.", source: "Day 079 교재1", meaning: null },
        { week: 16, ko: "A: 그럼 그냥 스카이로 먹겠습니다.", en: "A: Then I will settle for Sky.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "A: 아보카도 샐러드 주세요.", en: "A: I’ll have the avocado salad.", source: "Day 079 교재1", meaning: null },
        { week: 16, ko: "B: 죄송한데 아보카도가 다 떨어졌네요. 대신 치킨 샐러드 어떠실까요?", en: "B: Sorry, but we’re out of avocados. How about the chicken salad instead?", source: "Day 079 교재1", meaning: null },
        { week: 16, ko: "A: 뭐라고요? 정말요? 그럼 그냥 치킨 샐러드 주세요.", en: "A: What? Really? I guess I’ll just settle for the chicken salad, then.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "73분간 1점 차로 지고 있다가 환상적인 공격으로 동점을 만들었습니다. 시간만 조금 더 있었더라면 이길 수도 있었습니다. 하지만 무승부에 만족할 수밖에 없었네요.", en: "After being down by one for 73 minutes, we came back with a brilliant attack and tied it up. We probably could’ve won with a little more time, but we had to settle for a draw.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "원래는 좀 더 최신 모델을 원했는데 너무 비싸더라고요. 그래서 작년 모델에 만족해야 했어요.", en: "I wanted the newer model, but it was way out of my price range. I just settled for last year’s model, instead.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "정말 Rachel이랑 Dave를 위해 자리 마련해 주려고? Rachel은 아무 남자에게나 만족하지 않을 거라는 거 알면서.", en: "You really want to set Rachel up with Dave? You know she won’t settle for just any guy.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "신혼여행을 유럽으로 가고 싶었지만 여행 제한 시기에 결혼을 하는 바람에 제주도에 만족할 수밖에 없었다.", en: "We wanted to go to Europe for our honeymoon, but since we got married during travel restrictions, we had to settle for Jeju Island instead.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "마트에서 염소 치즈를 사려고 했지만 (없어서) 할 수 없이 페타 치즈에 만족해야만 했다.", en: "I was looking for goat cheese at the grocery store, but I had to settle for feta cheese instead.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "이번 주말에 원래는 한강에서 피크닉을 하고 싶었는데, 비가 오는 바람에 결국 할 수 없었다. 대신 보드게임 카페에서 체스 게임을 하는 것으로 만족해야만 했다.", en: "We were hoping to have a picnic by the Han River this weekend, but it ended up raining. We had to settle for playing chess at a board game café, instead.", source: "Day 079 교재1", meaning: meanings["settle for_1"] },
        { week: 16, ko: "나 최근에 생긴 비건 피자 가게 가 볼까 하는데. 보니까 독특한 맛이 여러 가지 많은가 봐. 후기도 좋더라고.", en: "I’m planning on checking out that new vegan pizza place that just opened. Apparently, they have a lot of unique toppings. It’s been getting great reviews.", source: "Day 079 교재2", meaning: null },
        { week: 16, ko: "근데 이 집 피자에는 고기가 안 올라가잖아. 두부나 고기 대용 재료에 만족해야 해.", en: "There’s no meat on their pizza, though. You would have to settle for tofu or meat substitutes.", source: "Day 079 교재2", meaning: meanings["settle for_1"] },
        { week: 16, ko: "(제) 아내는 원래 의사나 변호사 같은 전문직인 사람과 결혼하길 원했어요. 그래서 처음에는 저 같은 회사원에 만족할 리가 없다고 생각했답니다.", en: "She always wanted to marry a professional, like a doctor or a lawyer. At first, I thought there was no way she would settle for an office worker like me.", source: "Day 079 교재2", meaning: meanings["settle for_1"] },
        { week: 16, ko: "근데 어떻게 마음을 돌리게 만들었어요? 비결이 뭔가요? 두 분 지금은 천생연분 같아요!", en: "Then how did you get her to change her mind? What was your secret? You two seem like a match made in heaven now!", source: "Day 079 교재2", meaning: null },
        { week: 16, ko: "지난 주말에 정전이 장난이 아니었잖아요. 아내분이랑 결국 뭐 했어요?", en: "That power outage last weekend was crazy! What did you and your wife end up doing?", source: "Day 079 교재2", meaning: null },
        { week: 16, ko: "음, 원래는 집에서 넷플릭스 보면서 쉬려고 했는데, 정전이 되는 바람에 그냥 시간 보내려고 사진첩을 훑어봤어요.", en: "Well, our plan was to watch Netflix and chill at home, but since the power was out, we settled for looking through our photo albums to pass the time.", source: "Day 079 교재2", meaning: meanings["settle for_1"] },
        { week: 16, ko: "내 드림카를 소유하는 것은 평생의 목표였다. 하지만 내가 생각하고 있던 모델은 너무 비싸다.", en: "Owning my dream car has been a lifelong goal, but the model I had in mind is way too expensive.", source: "Day 079 교재3", meaning: null },
        { week: 16, ko: "그래도 내년에는 살 수 있는 방법을 찾아보려고 했다. 그런데 최근 딜러를 방문해 보고는 판단이 섰다.", en: "I was still trying to find some way to make the purchase next year, when a recent visit to the dealer gave me some perspective.", source: "Day 079 교재3", meaning: null },
        { week: 16, ko: "딜러 측에서는 조금 더 저렴한 모델을 생각해볼 것을 제안했다. 프로 레이싱 같은 걸 원하는 게 아니라면 (조금 더 저렴한 모델로도) 나의 니즈를 충분히 충족시킬 것이라고 했다.", en: "They suggested I consider a less expensive model, saying it would more than meet my needs unless I wanted to do something like pro racing.", source: "Day 079 교재3", meaning: null },
        { week: 16, ko: "고민을 좀 해 봤는데, 아무래도 이 대안에 만족해야 할 것 같다.", en: "After some thought, I think I will have to settle for this alternative.", source: "Day 079 교재3", meaning: meanings["settle for_1"] },
        { week: 16, ko: "하긴 이 정도도 충분히 고급 모델이다. 이 모델을 가질 수 있는 것도 행운인 셈이다.", en: "It’s still a luxurious choice, after all, and I’d be lucky to own it.", source: "Day 079 교재3", meaning: null },
        { week: 16, ko: "A: Jerry는 늘 자신의 하버드 티셔츠를 입고 헬스장에 가더라.", en: "A: Jerry always wears his Harvard t-shirt to the gym.", source: "Day 080 교재1", meaning: null },
        { week: 16, ko: "B: 맞아. 여자애들에게 잘 보이려고 그러는 거지. 하긴, 자랑할 근육은 없잖아.", en: "B: Yeah, he’s trying to show off to impress some girls. He has no muscles to show off, after all.", source: "Day 080 교재1", meaning: meanings["show off_1"] },
        { week: 16, ko: "A: 어젯밤 소개팅은 어땠어?", en: "A: How was that blind date you went on last night?", source: "Day 080 교재1", meaning: null },
        { week: 16, ko: "B: 최악이었어. 남자가 밤새 자기 자랑을 하더라고.", en: "B: Awful. The guy just bragged about himself the whole night.", source: "Day 080 교재1", meaning: meanings["brag about_1"] },
        { week: 16, ko: "A: 나만 인스타에 올릴 멋진 게 없는 건가?", en: "A: Am I the only one who has nothing cool to post on Instagram?", source: "Day 080 교재1", meaning: null },
        { week: 16, ko: "B: 그 사람들(인스타에 멋진 사진을 올리는 사람들)은 그냥 과시하려고 그러는 거야. 너는 (굳이 안 그래도) 멋지잖아.", en: "B: Those people are just showing off. I think you’re cool.", source: "Day 080 교재1", meaning: meanings["show off_1"] },
        { week: 16, ko: "A: 자랑하려는 건 아니고, 올해 내 사업은 정말 상승세를 타고 있어.", en: "A: I don’t mean to brag about this, but my business has really taken off this year.", source: "Day 080 교재1", meaning: meanings["brag about_1"] },
        { week: 16, ko: "B: 좋은 소식이다. 정말 잘됐다.", en: "B: That’s great news. I’m happy for you.", source: "Day 080 교재1", meaning: null },
        { week: 16, ko: "어서 하와이에 가서 (나의) 새로 만든 비키니 몸매를 과시하고 싶어!", en: "I can’t wait to show off my new bikini body in Hawaii!", source: "Day 080 교재2", meaning: meanings["show off_1"] },
        { week: 16, ko: "여보, 당신 틀림없이 멋져 보일 거야. 다이어트 정말 열심히 했으니까.", en: "I’m sure you’ll look amazing, honey. You’ve worked so hard on your diet.", source: "Day 080 교재2", meaning: null },
        { week: 16, ko: "사람들이 롤렉스 시계에 열광하는 이유를 모르겠어.", en: "I don’t really get why everyone’s crazy about Rolex watches.", source: "Day 080 교재2", meaning: null },
        { week: 16, ko: "음, 어떤 사람들에게는 (시계라는 것이) 단순히 시간을 확인하는 것 이상의 의미거든. 신분이자 부를 과시하는 것이지.", en: "Well, for some, it’s more than just telling time; it’s about status and showing off wealth.", source: "Day 080 교재2", meaning: meanings["show off_1"] },
        { week: 16, ko: "Nick이 (자기가) 아마추어 보디빌딩 대회에서 우승한 거 자랑하는 거 들었어?", en: "Did you hear Nick bragging about winning that amateur body building competition?", source: "Day 080 교재2", meaning: meanings["brag about_1"] },
        { week: 16, ko: "응, 최근에 운동 중독인 듯해. 그 친구 있는 데서 운동 이야기는 꺼내지 마. 몇 시간이고 계속 떠들 거야.", en: "Yeah, he seems addicted to workouts lately. Don’t even bring it up around him. He’ll go on for hours.", source: "Day 080 교재2", meaning: null },
        { week: 16, ko: "구직자의 경우 면접 때 자신이 이룬 것을 과시하는 것이 중요합니다.", en: "As job seekers, it’s important to show off your achievements during interviews.", source: "Day 080 교재3", meaning: meanings["show off_1"] },
        { week: 16, ko: "그동안 거둔 성공과 능력을 자신 있게 강조해야 합니다.", en: "You should highlight your successes and skills with confidence.", source: "Day 080 교재3", meaning: null },
        { week: 16, ko: "달리 말해, 자신이 이룬 것에 대해 자랑하는 것을 주저하지 마세요.", en: "In other words, don’t be shy about bragging about your accomplishments.", source: "Day 080 교재3", meaning: meanings["brag about_1"] },
        { week: 16, ko: "(면접에서는) 어떻게 자신을 보여 주는지가 중요합니다. 너무 겸손하고 소심하면 자칫 자신감 없어 보일 수 있습니다.", en: "How you present yourself is important; if you are too humble or shy, you might come off as being less confident.", source: "Day 080 교재3", meaning: null },
        { week: 16, ko: "요즘 고용 시장에서의 채용자들은 자신감 있는 사람에게 끌립니다.", en: "Employers in the job market today are attracted to confident people.", source: "Day 080 교재3", meaning: null },
        { week: 16, ko: "자신이 그 자리에 적임자라고 판단되면 반드시 능력이 있다는 인상을 주셔야 합니다. 실제로 당신은 능력이 있으니까요.", en: "So as long as you believe you’re qualified for the position, make sure you come across as capable, because you are.", source: "Day 080 교재3", meaning: null },
        
        // Week 17
        { week: 17, ko: "아빠가 쓰는 공구들 가지고 장난 그만 좀 쳐! 위험한 것들이 있단 말이야.", en: "Don’t mess around with your dad’s tools! Some of them are dangerous.", source: "Day 081 교재1", meaning: meanings["mess around_1"] },
        { week: 17, ko: "제가 음악가는 아니지만 시간이 날 때면 드럼을 가지고 노는 걸 좋아합니다.", en: "I’m not a musician, but I like to mess around with the drums when I can.", source: "Day 081 교재1", meaning: meanings["mess around_1"] },
        { week: 17, ko: "오후 내내 보고서 마무리는 안 하고 휴대폰 하는 데 시간을 허비했다.", en: "I spent the whole afternoon messing around with my phone instead of finishing my report.", source: "Day 081 교재1", meaning: meanings["mess around_2"] },
        { week: 17, ko: "미안해. (네) 기분 상하게 할 의도는 없었어. 그냥 장난친 거라고.", en: "I’m sorry. I didn’t mean for you to take that as an insult. I was just trying to mess around.", source: "Day 081 교재1", meaning: meanings["mess around_3"] },
        { week: 17, ko: "그 둘은 그냥 재미로 만나는 거야. 둘 다 당장은 사귄다는 걸 알릴 마음이 없어.", en: "They’re just messing around; neither of them is planning on making it official anytime soon.", source: "Day 081 교재1", meaning: meanings["mess around_4"] },
        { week: 17, ko: "휴대폰 그만 만지작거려. 이제 자러 가야 할 시간이야.", en: "Stop messing around with your phone. It’s time to go to bed.", source: "Day 081 교재1", meaning: meanings["mess around_1"] },
        { week: 17, ko: "제 아들이 시험공부를 해야 함에도 비디오 게임을 하면서 계속 빈둥거리네요.", en: "My son keeps messing around with video games when he should be studying for his exams.", source: "Day 081 교재1", meaning: meanings["mess around_2"] },
        { week: 17, ko: "Andrew, 동생 좀 그만 놀리렴. 또 한 번 울리면 아빠한테 이른다.", en: "Stop messing around with your brother, Andrew. If you make him cry again, I’m telling your dad.", source: "Day 081 교재1", meaning: meanings["mess around_3"] },
        { week: 17, ko: "이제 여러 이성을 만나는 것도 지겹습니다. 정착해서 몇 년 안에 결혼하고 싶네요.", en: "I am tired of messing around. I want to settle down and get married within the next few years.", source: "Day 081 교재1", meaning: meanings["mess around_4"] },
        { week: 17, ko: "너희들 그룹 프로젝트 마무리하는 데 얼마나 걸렸어?", en: "How long did it take for you guys to finish the group project?", source: "Day 081 교재2", meaning: null },
        { week: 17, ko: "10시간 정도. 근데 계속해서 작업을 한 건 아니야. 끝나갈 무렵에는 슬슬 놀면서 했어.", en: "About 10 hours, but it wasn’t like we were working the whole time. Near the end, we were pretty much just messing around.", source: "Day 081 교재2", meaning: meanings["mess around_2"] },
        { week: 17, ko: "정말 이 머리 스타일 나한테 안 어울리는 거 같아? 여자 친구는 귀엽다고 했거든.", en: "Do you really think this hairstyle looks bad on me? My girlfriend said it looks cute.", source: "Day 081 교재2", meaning: null },
        { week: 17, ko: "아니야. 그냥 농담한 거야. 귀여워.", en: "No. I was just messing around. It’s cute.", source: "Day 081 교재2", meaning: meanings["mess around_3"] },
        { week: 17, ko: "이제 더 이상 이런 연애 안 할래. 나랑 결혼 안 할 거면 우리 끝내자.", en: "I am done messing around. If you are not going to marry me, then we are through.", source: "Day 081 교재2", meaning: meanings["mess around_4"] },
        { week: 17, ko: "내가 결혼을 원하지 않는다고 해서 집중을 안 하는 건 아니잖아. 결혼하지 않고도 서로에게 충실할 수는 없을까?", en: "Just because I don’t want to get married, that doesn’t mean I’m messing around. Can’t we be committed to each other without making things official?", source: "Day 081 교재2", meaning: meanings["mess around_4"] },
        { week: 17, ko: "자, 이제 신년도 되었으니 나쁜 습관 세 가지를 고치기로 결심했다.", en: "Well, it’s the start of a new year, and I’ve decided to work on three of my bad habits.", source: "Day 081 교재3", meaning: null },
        { week: 17, ko: "우선 나는 회사에 제시간에 출근하는 것을 정말 못한다.", en: "First of all, I’m terrible at getting to work on time.", source: "Day 081 교재3", meaning: null },
        { week: 17, ko: "늦는 경우가 많아서 이 때문에 여러 번 지적을 받았다.", en: "I’m usually late and have been reprimanded multiple times because of it.", source: "Day 081 교재3", meaning: null },
        { week: 17, ko: "솔직히 출근하기가 너무 싫어서 출근 전에 30분 정도 뭉그적거리는 버릇이 있다.", en: "Honestly, before leaving for work, I tend to mess around for like 30 minutes because I just don’t want to go.", source: "Day 081 교재3", meaning: meanings["mess around_2"] },
        { week: 17, ko: "두 번째로 여가 시간을 좀 더 효과적으로 보낼 필요가 있다.", en: "Second, I need to use my free time more effectively.", source: "Day 081 교재3", meaning: null },
        { week: 17, ko: "최근에는 퇴근 후에 아무 생각 없이 유튜브를 보거나 SNS를 하게 된다.", en: "Lately, when I get home from work, I just end up mindlessly watching YouTube or checking social media.", source: "Day 081 교재3", meaning: null },
        { week: 17, ko: "이런 무의미한 시간을 좀 더 나은 사람이 될 수 있는 취미에 쓰면 더 좋다는 것을 알고 있다. 하지만 노력을 해도 잘 안된다.", en: "I know my time could be better spent on hobbies that make me a better person, but I just can’t get myself to do them.", source: "Day 081 교재3", meaning: null },
        { week: 17, ko: "마지막으로 제때 취침을 해야겠다.", en: "Last, I’m going to start going to bed on time.", source: "Day 081 교재3", meaning: null },
        { week: 17, ko: "수면 부족으로 건강이 나빠지고 있다.", en: "A lack of sleep has been taking a toll on my health.", source: "Day 081 교재3", meaning: null },
        { week: 17, ko: "공연 때 대사 몇 개를 잘못 말했지 뭐야.", en: "During the play, I messed up several of my lines.", source: "Day 082 교재1", meaning: meanings["mess up_1"] },
        { week: 17, ko: "올림픽에서는 설사 실수를 하더라도 아무 일 없었다는 듯 행동해야 해.", en: "When you mess up in the Olympics, you’re supposed to act gracefully about it.", source: "Day 082 교재1", meaning: meanings["mess up_1"] },
        { week: 17, ko: "내가 제일 좋아하는 음식이 프라이드치킨인데, 먹을 때마다 속이 뒤집어진다는 점이 문제야.", en: "My favorite food is fried chicken, but it messes up my stomach every time.", source: "Day 082 교재1", meaning: meanings["mess up_2"] },
        { week: 17, ko: "연습하는 동안 계속 이 춤 동작을 실수하게 된다. 이번 주말 무대에서도 내가 실수할까 봐 우리 팀원들이 걱정하고 있다.", en: "I keep messing up this particular dance move during practice. My team is getting worried that I might mess up on stage this weekend, too.", source: "Day 082 교재1", meaning: meanings["mess up_1"] },
        { week: 17, ko: "내 머리 좀 만지지 마. (자꾸 만지면) 엉망이 될 거야. 아침에 20분이나 들여서 머리 예쁘게 만졌단 말이야.", en: "Stop touching my hair. You are gonna mess it up. I spent 20 minutes this morning getting it just right.", source: "Day 082 교재1", meaning: meanings["mess up_2"] },
        { week: 17, ko: "그가 취소하는 바람에 제 스케줄 전체가 꼬여 버렸습니다.", en: "His cancellation has messed up my whole schedule.", source: "Day 082 교재1", meaning: meanings["mess up_2"] },
        { week: 17, ko: "예상치 못한 일이 생겨 일상이 꼬이는 건 싫다.", en: "I don’t like when unexpected things mess up my routine.", source: "Day 082 교재1", meaning: meanings["mess up_2"] },
        { week: 17, ko: "Nick, 나 실수한 것 같아. 여자 친구에게 내 폰을 보여 주고 있는데, 다른 여자가 내게 메시지를 보냈어.", en: "Nick, I think I messed up. While I was letting my girlfriend look at my phone, another girl messaged me.", source: "Day 082 교재2", meaning: meanings["mess up_1"] },
        { week: 17, ko: "버너폰을 가지고 다녀야 한다고 내가 말했잖아!", en: "I told you to carry a burner phone!", source: "Day 082 교재2", meaning: null },
        { week: 17, ko: "생일이라고 해서 케이크를 만들어 주려 하다가, 베이킹파우더를 너무 많이 넣는 바람에 망쳤네요.", en: "I tried to make you a cake for your birthday, but I messed it up by putting in too much baking powder.", source: "Day 082 교재2", meaning: meanings["mess up_1"] },
        { week: 17, ko: "그래도 만들어 주려고 한 게 정말 고맙군요. 이 케이크 너무 “고마워서” 먹을 수가 없네요. 대신 아이스크림 먹으러 가요.", en: "How sweet of you for trying, though. I “appreciate” this cake too much to eat it. Let’s go get ice cream, instead.", source: "Day 082 교재2", meaning: null },
        { week: 17, ko: "아메리카노 사 왔어.", en: "I bought you an Americano.", source: "Day 082 교재2", meaning: null },
        { week: 17, ko: "아, 미안해. 나 커피 마시면 안 돼. 커피를 안 좋아하는 게 아니고, 카페인을 섭취하면 머리가 아프거든.", en: "Oh, I’m sorry. I can’t have any coffee. It’s not that I don’t like coffee. It’s just that caffeine messes me up.", source: "Day 082 교재2", meaning: meanings["mess up_2"] },
        { week: 17, ko: "나는 해외여행을 할 때 시차 때문에 힘든 일이 잘 없다.", en: "I normally don’t suffer from jet lag when I travel abroad.", source: "Day 082 교재3", meaning: null },
        { week: 17, ko: "이유는 잘 모르겠지만, 아마 다른 나라에 간다는 게 너무 설레서일지도 모르겠다.", en: "I’m not sure why, though; maybe because I’m always excited to be in a different country.", source: "Day 082 교재3", meaning: null },
        { week: 17, ko: "하지만 지난달 사장님으로부터 업무 회의차 토론토 출장을 가야 한다는 말을 들었고, 그날 밤 바로 출발해야 한다고 했다.", en: "However, last month I was told by my boss that I needed to fly to Toronto for a business conference, and that I would need to leave that night.", source: "Day 082 교재3", meaning: null },
        { week: 17, ko: "회의 준비는커녕 집에 가서 짐을 챙길 시간도 거의 없었다.", en: "I barely had time to go home and pack, let alone prepare for business meetings.", source: "Day 082 교재3", meaning: null },
        { week: 17, ko: "4일 동안 토론토에 있었고 회의는 잘 끝났지만, 출장에서 돌아온 후 계속 수면이 엉망인 상태가 이어지고 있다.", en: "I was there for four days and the meetings went fine, but my sleep has been messed up ever since I got back.", source: "Day 082 교재3", meaning: meanings["mess up_2"] },
        { week: 17, ko: "음악 좀 바꿔 줄래? 기분이 우울해지잖아.", en: "Can you change the music? It’s messing with my mood.", source: "Day 083 교재1", meaning: meanings["mess with_1"] },
        { week: 17, ko: "더 이상 Brandon이랑은 엮이기 싫어(안 놀아). 내 화를 돋워 싸움을 시작하게 하는 말만 한다니까.", en: "I don’t mess with Brandon anymore. He knows exactly what to say to rile me up and start a fight.", source: "Day 083 교재1", meaning: meanings["mess with_2"] },
        { week: 17, ko: "저는 출근할 때 더 이상 버스는 안 탑니다. 예측이 어렵고 (버스 타서) 지각한 적이 너무 많습니다.", en: "I don’t mess with the bus system anymore to get to work. It’s unpredictable and it made me late too many times.", source: "Day 083 교재1", meaning: meanings["mess with_2"] },
        { week: 17, ko: "그냥 한 말이야. 너무 예민하게 굴지 마.", en: "I was just messing with you. Don’t be so sensitive.", source: "Day 083 교재1", meaning: meanings["mess with_3"] },
        { week: 17, ko: "이봐, 내 카메라 설정 건드린 거야? 새로 찍은 사진이 죄다 과다 노출로 나오잖아.", en: "Hey, did you mess with the settings on my camera? All my new photos are overexposed.", source: "Day 083 교재1", meaning: meanings["mess with_4"] },
        { week: 17, ko: "늦은 시간에 커피 마시지 말아야겠어. 수면에 방해가 돼.", en: "I have to stop drinking coffee late; it messes with my sleep.", source: "Day 083 교재1", meaning: meanings["mess with_1"] },
        { week: 17, ko: "더 이상 술은 안 마십니다. 술 마셔서 좋을 게 하나도 없는 것 같아서요.", en: "I don’t mess with alcohol anymore. It just seems like nothing good ever comes out of drinking.", source: "Day 083 교재1", meaning: meanings["mess with_2"] },
        { week: 17, ko: "식중독 걸린 이후로는 여행 중에 길거리 음식은 안 먹습니다.", en: "Ever since I got food poisoning, I don’t mess with street food on my travels.", source: "Day 083 교재1", meaning: meanings["mess with_2"] },
        { week: 17, ko: "제 친구는 자기가 일본인인 양 메뉴판을 읽지 못하는 척하면서 식당 직원을 골탕 먹이는 버릇이 있습니다. 멍청한 녀석이죠.", en: "My friend likes to mess with servers by pretending he’s Japanese and can’t read the menu. He’s kind of a jerk.", source: "Day 083 교재1", meaning: meanings["mess with_3"] },
        { week: 17, ko: "내가 나가 있는 동안 누가 내 태블릿 건드린 거야? 내가 다운 받지도 않은 앱이 엄청 있네.", en: "Who messed with my new tablet while I was gone? There’s a bunch of apps that I didn’t download on it.", source: "Day 083 교재1", meaning: meanings["mess with_4"] },
        { week: 17, ko: "주방에 있는 분은 건드리면 안 된다는 걸 비싼 대가를 치르고 알게 되었어요. 다음 날 식중독으로 병원 신세를 지게 되었습니다.", en: "I learned the hard way not to mess with kitchen staff. I ended up in the hospital with food poisoning the next day.", source: "Day 083 교재1", meaning: meanings["mess with_5"] },
        { week: 17, ko: "다음 …시에 …하자, …알았지?", en: "Let’s… at… o’clock… next… okay?", source: "Day 083 교재2", meaning: null },
        { week: 17, ko: "뭐라고? 끊겨서 들려. 지하라서 신호가 끊기는 것 같아. 내려서 다시 전화할게.", en: "Sorry? You’re breaking up. I think being underground is messing with my signal. I’ll call you back when I get off.", source: "Day 083 교재2", meaning: meanings["mess with_1"] },
        { week: 17, ko: "내일 만우절이라 학생들 좀 골탕 먹이려고요.", en: "I am going to mess with my students tomorrow for April Fool’s Day.", source: "Day 083 교재2", meaning: meanings["mess with_3"] },
        { week: 17, ko: "진짜요? 어떤 계획인가요? 저도 같이 아이들 놀려 볼까 싶네요.", en: "Oh really? What do you have planned? Maybe I’ll get in on it with you.", source: "Day 083 교재2", meaning: null },
        { week: 17, ko: "Johnny가 뭐라고 했는지 들었어? 누가 걔 좀 혼내 줘야 해.", en: "Did you hear what Johnny said? Someone should teach him a lesson.", source: "Day 083 교재2", meaning: null },
        { week: 17, ko: "걔는 건들지 마. 이 동네에서 제일 센 녀석들이랑 친구니까.", en: "Don’t mess with him. He’s friends with some of the strongest guys in town.", source: "Day 083 교재2", meaning: meanings["mess with_5"] },
        { week: 17, ko: "안녕하세요, 여러분! 오 박사님이 오늘 함께 해 주셨습니다. 알코올 섭취와 과음의 기준에 대해 한 말씀해 주실 겁니다. 박사님, 시작하시죠.", en: "Hello, everyone! Dr. Oh is with us today to teach us a bit about alcohol consumption, and how much is too much. Doctor, please go ahead.", source: "Day 083 교재3", meaning: null },
        { week: 17, ko: "감사합니다. 아시다시피 많은 한국인이 퇴근 후 술 한잔하면서 긴장을 푸는 것을 좋아하지만, 문제는 말씀하신 것처럼, 어느 정도가 과한 것일까요?", en: "Thank you. As we all know, a lot of Koreans like to kick back with a few drinks after getting off work, but the question is, as you said, how much is too much?", source: "Day 083 교재3", meaning: null },
        { week: 17, ko: "사실 술은 조금만 마신다고 해도 너무 자주 마실 경우에는 건강에 해롭습니다.", en: "Actually, consuming even a little alcohol too frequently can have negative effects on our health.", source: "Day 083 교재3", meaning: null },
        { week: 17, ko: "우선 수면의 질을 떨어뜨립니다.", en: "First and foremost, alcohol really messes with your quality of sleep.", source: "Day 083 교재3", meaning: meanings["mess with_1"] },
        { week: 17, ko: "술을 먹어야겠다면 주 1회로 제한해야 하고, 적당히 마셔야 합니다.", en: "If you feel the need to indulge, you should limit yourself to drinking once a week, and in moderation.", source: "Day 083 교재3", meaning: null },
        { week: 17, ko: "오늘 밤에 나와. 파티 안 가면 후회할 거야.", en: "Hey, come out tonight. You don’t want to miss the party.", source: "Day 084 교재1", meaning: null },
        { week: 17, ko: "A: 아파서 지난 주말 콘서트에 못 갔다며. 맞아?", en: "A: I heard you were sick and couldn’t make it to the concert last weekend. Is that right?", source: "Day 084 교재1", meaning: null },
        { week: 17, ko: "B: 응. 정말 가고 싶었는데 전날 독감에 걸렸어.", en: "B: Yeah. I was really looking forward to it, but I got the flu the day before.", source: "Day 084 교재1", meaning: null },
        { week: 17, ko: "A: 정말 안됐다! 너무 좋은 기회를 놓쳤네! 정말 멋진 시간이었는데.", en: "A: Too bad! You really missed out! It was an amazing time.", source: "Day 084 교재1", meaning: meanings["miss out_1"] },
        { week: 17, ko: "지민 씨, 토요일 회의하기 전에 아팠다면서요. 걱정 마세요. (회의 때) 이렇다 할 특별한 내용은 없었어요.", en: "Hey Jimin, I heard you got sick before Saturday’s meeting. Don’t worry. You didn’t miss out on anything.", source: "Day 084 교재1", meaning: meanings["miss out_1"] },
        { week: 17, ko: "파티를 즐길 수 있는 기회 혹은 상사랑 술 마실 수 있는 기회를 놓치고 싶지 않거든.", en: "I don’t want to miss out on the party or on getting to drink with the boss.", source: "Day 084 교재1", meaning: meanings["miss out_1"] },
        { week: 17, ko: "A: 우리 가족들이 하와이에 가는데, 나는 일이 바쁘다고 했어.", en: "A: My family is going to Hawaii, but I told them I was too busy at work.", source: "Day 084 교재1", meaning: null },
        { week: 17, ko: "B: 뭐라고? 하와이 여행을 마다하는 게 말이 돼?", en: "B: What? Why would you want to miss out on a trip to Hawaii?", source: "Day 084 교재1", meaning: meanings["miss out_1"] },
        { week: 17, ko: "이건 너무 중요한 기회야! 절대로 그냥 보내지 않을 거야.", en: "This is a huge chance! I’m not going to miss out on it.", source: "Day 084 교재1", meaning: meanings["miss out_1"] },
        { week: 17, ko: "아파서 스키 여행 갈 수 있는 기회를 놓치다니. 너무 속상해!", en: "I can’t believe I missed out on the ski trip because I was sick. What a bummer!", source: "Day 084 교재1", meaning: meanings["miss out_1"] },
        { week: 17, ko: "도산대로에서 하는 Montana Choi의 파티에 꼭 와. 인맥을 쌓을 수 있는 기회를 놓치면 안 되니까.", en: "You have to come to Montana Choi’s party on Dosan Street. You don’t want to miss out on a chance to network.", source: "Day 084 교재2", meaning: meanings["miss out_1"] },
        { week: 17, ko: "알아. 나도 꼭 가서 그분과 친해지고 싶었어. 근데 내 스케줄을 확실히 모르겠어. 수요일까지 알려줘도 돼?", en: "I know. I was really hoping to go and get acquainted with him. I’m still not sure about my schedule, though. Can I let you know by Wednesday?", source: "Day 084 교재2", meaning: null },
        { week: 17, ko: "회식은 나랑 안 맞아. 상사가 소주를 강요하는 게 너무 싫거든.", en: "Team dinners aren’t really for me. I don’t like that supervisors insist on me drinking soju.", source: "Day 084 교재2", meaning: null },
        { week: 17, ko: "나도 마찬가지야. 나도 회사 회식 가는 거 싫어. 그래도 흥미로운 소소한 이야기를 놓치고 싶지 않아서 여전히 가긴 해.", en: "Same here. I don’t like going out to company dinners, either. But I still go because I don’t want to miss out on the juicy small talk.", source: "Day 084 교재2", meaning: meanings["miss out_1"] },
        { week: 17, ko: "못 오실 줄 알았더니 오셔서 다행입니다. (이번 행사를) 꼭 경험하시길 바랐거든요. 멋진 안경도 보시고 패션 쪽 사람들과도 어울릴 좋은 기회일 거예요.", en: "Well, I’m glad you could make it. I didn’t want you to miss out. It will be a good chance to check out these amazing glasses and mingle with people in the fashion industry.", source: "Day 084 교재2", meaning: meanings["miss out_1"] },
        { week: 17, ko: "팝업 행사 초대해 줘서 고맙습니다. 진짜 기대했습니다. 그나저나 안경테 추천해 주실 만한 것 있을까요?", en: "Thanks for inviting me to the pop-up event. I was really looking forward to it. Are there any particular frames you would recommend, by the way?", source: "Day 084 교재2", meaning: null },
        { week: 17, ko: "아무래도 SNS를 완전히 끊어야 할 것 같다. 특히 인스타그램을 말이다.", en: "I feel like I should quit social media altogether, especially Instagram.", source: "Day 084 교재3", meaning: null },
        { week: 17, ko: "친구들이 끊임없이 휴가를 보내거나 밤에 나가서 노는 걸 보면 다른 사람들은 인생을 충분히 즐기는데 나만 소외된 느낌이 든다.", en: "Seeing my friends constantly on holiday or enjoying nights out can make me feel like I am missing out while others are living their life to the fullest.", source: "Day 084 교재3", meaning: meanings["miss out_1"] },
        { week: 17, ko: "최근 우연히 보게 된 기사를 한번 보자.", en: "Take a look at this article I recently came across.", source: "Day 084 교재3", meaning: null },
        { week: 17, ko: "내용은 이렇다. “SNS는 사람들에게 비현실적인 기대를 갖게 하고, 자존감이 낮아지게 만든다. 인스타그램 때문에 여성들이 자신의 외모가 부족하다고 느끼게 된다.”", en: "It goes like this: “Social media posts can also set unrealistic expectations and create feelings of low self-esteem. Instagram easily makes girls and women feel as if their bodies aren’t good enough.”", source: "Day 084 교재3", meaning: null },
        { week: 17, ko: "여성으로서 이 기사에서 여자가 한 말에 너무 공감이 간다. 여러분은 어떤가?", en: "As a woman, I couldn’t agree more with what she said in the article. How do you feel?", source: "Day 084 교재3", meaning: null },
        { week: 17, ko: "A: Haley, 어젯밤 데이트는 어땠어?", en: "A: Haley, how was your date last night?", source: "Day 085 교재1", meaning: null },
        { week: 17, ko: "B: 너무 좋았어. 저녁 먹고, 조용한 와인바로 이동해서 몇 시간 동안 이야기를 나누었어. 이 남자가 내가 찾던 남자라는 생각이 들어.", en: "B: It was amazing. We had dinner and moved on to a quiet wine bar where we talked for hours. I really think this guy is the one.", source: "Day 085 교재1", meaning: meanings["move on_1"] },
        { week: 17, ko: "지하철에서 우연히 전 여자 친구를 마주쳤는데도 아무렇지도 않더군요. 그제서야 이제는 잊고 새출발해도 되겠구나 싶었습니다.", en: "I knew I was ready to move on when I ran into my ex on the subway and I felt completely normal around her.", source: "Day 085 교재1", meaning: meanings["move on_3"] },
        { week: 17, ko: "저는 하나의 업무를 완료하지 못하면 다음 일로 넘어가지 못하는 사람입니다. 멀티태스킹에 능한 사람이 아닙니다.", en: "I’m the kind of person who can’t move on until I completely finish a task. I’m not a multi-tasker.", source: "Day 085 교재1", meaning: meanings["move on_2"] },
        { week: 17, ko: "뉴욕에 3년 살았는데, 정말 좋은 경험이었습니다. 하지만 이젠 다른 도시에 가서 살 때가 된 것 같아요.", en: "I’ve lived in New York for three years and I’m really glad for the experience. But now, I think I am ready to move on.", source: "Day 085 교재1", meaning: meanings["move on_3"] },
        { week: 17, ko: "답을 모르겠으면, 다음 문제로 넘어갔다가 쉬운 것을 다 풀고 난 후에 다시 풀어 봐.", en: "When you don’t know the answer to a question, move on and try again when you’ve finished the easier ones.", source: "Day 085 교재1", meaning: meanings["move on_2"] },
        { week: 17, ko: "Sarah가 이번 주말에 소개팅하기로 했어. 전 남자 친구를 굉장히 빨리 잊는 것 같아.", en: "Sarah’s going on a blind date this weekend. I guess she moves on really fast.", source: "Day 085 교재1", meaning: meanings["move on_3"] },
        { week: 17, ko: "스캔들 이후에 그의 팬 중 많은 이들의 마음이 이미 떠난 상태다.", en: "Following the scandal, many of his fans have already moved on.", source: "Day 085 교재1", meaning: meanings["move on_4"] },
        { week: 17, ko: "이제 다음으로 넘어가도 될 것 같네요. 다음 슬라이드 띄우겠습니다.", en: "I think we’re ready to move on, so I’ll just pull up the next slide.", source: "Day 085 교재2", meaning: meanings["move on_2"] },
        { week: 17, ko: "잠시만요. 배터리 셀 부분을 좀 더 자세히 설명해 주실 수 있을까요? 그 부분이 조금 이해가 안 돼서요.", en: "Wait a second. Can you elaborate more on battery cells? You lost me a bit there.", source: "Day 085 교재2", meaning: null },
        { week: 17, ko: "어젯밤에 Jeff랑 Hailey를 데리고 나가서 저녁 식사했다면서? 어땠어? 오늘 아침에 보니 Jeff 몰골이 말이 아니던데.", en: "I heard you took Jeff and Hailey out to dinner last night. How did it go? Jeff was looking pretty rough this morning when I saw him.", source: "Day 085 교재2", meaning: null },
        { week: 17, ko: "응, 맞아. 1차로 삼겹살 먹고 2차는 공덕역에 있는 ‘언포게터블’이라는 바에 갔어. Jeff가 고주망태가 되어 여자들에게 추파를 던지기 전까지는 좋았는데 말이야. Hailey는 엄청 화가 났지.", en: "Yeah, I did. We first went out for pork belly before moving on to a bar named “Unforgettable” at Gongdeok station. We were having a good time until Jeff got totally wasted and started hitting on some women. Hailey was furious.", source: "Day 085 교재2", meaning: meanings["move on_1"] },
        { week: 17, ko: "아직 지원이에게 감정이 남아 있는 거니? 벌써 6개월이 지났잖아. 과거에 연연하지 말고 새출발해야지.", en: "Are you still upset about Jiwon? It’s been six months already. You can’t let the past get in the way. It’s time to move on.", source: "Day 085 교재2", meaning: meanings["move on_3"] },
        { week: 17, ko: "그게 말처럼 쉽지가 않아. 그녀를 잊을 수가 없어. 헤어진 건 너무 큰 실수였다는 생각 밖에 안 들어.", en: "I wish it was that easy. I can’t get over her. All I can think about is what a huge mistake I made.", source: "Day 085 교재2", meaning: null },
        { week: 17, ko: "예전에는 Lady Gaga의 엄청난 팬이었다. 하지만 최근 앨범은 그냥 쉽게 돈 벌려고 만든 느낌이다.", en: "I used to be a huge fan of Lady Gaga, but her latest album just feels like a cash grab.", source: "Day 085 교재3", meaning: null },
        { week: 17, ko: "이제 그녀의 전성기는 끝난 것 같다. 왜 많은 팬들이 마음이 떠나고 있는지 알겠다.", en: "It looks like her peak time in the spotlight is over, and I can see why many fans are moving on.", source: "Day 085 교재3", meaning: meanings["move on_4"] },
        { week: 17, ko: "그녀는 더 이상 음악계에서 의미 있는 역할을 하지 못하는 듯하다.", en: "She just doesn’t seem to play a real role in the music scene anymore.", source: "Day 085 교재3", meaning: null },
        { week: 17, ko: "팬들과도 너무 동떨어져 있는 것 같다. 특히 SNS에서의 적극적인 활동이 너무 부족하다.", en: "It seems like she’s lost touch with fans, especially with her lack of engagement on social media.", source: "Day 085 교재3", meaning: null },
        { week: 17, ko: "최근에는 예술적인 완성도를 유지하기보다는 돈 버는 데 더 집중하는 것 같아서, 정말 실망스럽다.", en: "Lately, it feels like she’s more focused on making money than maintaining her artistic integrity, which has really disappointed me.", source: "Day 085 교재3", meaning: null }
    ];

    // 3. 영어회화 데이터 (Week 13~17)
    const rawConvData = [
        // Week 13
        { week: 13, source: "Day061 교재1", ko: "미안한데 잘 못 들었어요. 한 번만 더 이야기해 주시겠어요?", en: "Oh, I’m sorry. I didn’t catch that. Could you repeat it?" },
        { week: 13, source: "Day061 교재1", ko: "성함을 못 들은 것 같습니다.", en: "I’m afraid I didn’t catch your name." },
        { week: 13, source: "Day061 교재1", ko: "(이사한다는 말을 듣고) 날짜를 잘 못 들었어. 언제 다시 이사 간다고?", en: "I didn’t catch the date. When are you moving out again?" },
        { week: 13, source: "Day061 교재1", ko: "(발표자가 청중에게) 혹시 놓친 부분이 있을까요?", en: "Is there anything you weren’t able to catch?" },
        { week: 13, source: "Day061 교재1", ko: "예산에 관해 이야기하실 때 제가 발표 내용 일부를 놓쳤어요.", en: "I didn’t catch the part of your presentation when you talked about the budget." },
        { week: 13, source: "Day061 교재2", ko: "안녕하세요, 38 사이즈로 새 신발 있는지 문의드려요.", en: "Hello, I was wondering if you have the new shoes in size 38." },
        { week: 13, source: "Day061 교재2", ko: "죄송한데, 무슨 사이즈라고요? 잘 못 들었어요.", en: "I’m sorry? What size? I didn’t catch that." },
        { week: 13, source: "Day061 교재2", ko: "두 번째 책 제목이 뭐라고 했나요? 저희 집 고양이가 뭘 넘어뜨리는 바람에 못 들었어요.", en: "What did you say was the title of your second book? I didn’t catch that because my cat knocked something over." },
        { week: 13, source: "Day061 교재2", ko: "하하, 괜찮아요. 제 책에 관심 가져 주시는 것만으로도 좋은데요.", en: "Haha, no problem. I’m just glad you’re interested in my work." },
        { week: 13, source: "Day061 교재2", ko: "죄송한데, Kline 선생님? 3, 4번 문제 답을 못 들었어요.", en: "Excuse me, Mr. Kline? I didn’t catch the answers to numbers 3 and 4." },
        { week: 13, source: "Day061 교재2", ko: "아, 그래. 다시 불러 줄게.", en: "Ah, okay. I’ll give the answers again." },
        { week: 13, source: "Day061 교재3", ko: "(줌 회의 진행자가 참석자들에게)\n죄송한데 하시는 말씀이 잘 안 들립니다. 다들 회의 참여 전에 마이크가 되는지 꼭 확인 부탁드립니다. 다시 한번 말씀드리지만 뭘 드시거나 마시면 안 됩니다. 주의가 산만해질 수 있으니까요. 마지막으로, 반려동물이나 아이들은 다른 방에 두시는 것도 잊지 마세요.", en: "I’m sorry. I can’t catch what you’re saying. Everyone, please make sure that your mics are working before entering the meeting. As a reminder, you’re not supposed to eat or drink anything. That can be quite distracting. Finally, please make sure to keep your pets and children in another room." },
        { week: 13, source: "Day061 교재4", ko: "다시 한번 말씀해 주시겠어요? 소음 때문에 잘 못 들었어요.", en: "Could you say that again? I couldn’t quite make you out over all the noise." },
        { week: 13, source: "Day061 교재4", ko: "대충 들리는 말로는, 우리 기차가 10분 정도 늦게 대전역에 도착한다고 하네.", en: "From what I could make out, our train will get to Daejeon station maybe 10 minutes late." },
        { week: 13, source: "Day061 교재4", ko: "동양인들에게는 (미국식과는 다른) 영국식 억양이 알아듣기 힘들 수 있어요.", en: "For Asians, the different British accents can be hard to make out." },
        { week: 13, source: "Day061 대표", ko: "죄송해요. 못 들었어요.", en: "I’m sorry. I didn’t catch that." },
        { week: 13, source: "Day062 교재1", ko: "당신 어제 새벽 3시나 되어서 집에 들어온 데다, 술 냄새가 진동하더군. 오늘 아픈 게 당연한 거야.", en: "You didn’t get home until 3 a.m., and you reeked of alcohol. No wonder you feel sick today." },
        { week: 13, source: "Day062 교재1", ko: "너희 동네에서 시위가 있었다고 뉴스에서 들었어. 그래서 늦었구나.", en: "I heard on the news that there was a protest in your neighborhood. No wonder you’re late." },
        { week: 13, source: "Day062 교재1", ko: "그 사람은 패션 감각이 전혀 없어요. 그러니까 여자 친구가 안 생기죠.", en: "He has zero fashion sense. No wonder he can’t find a girlfriend." },
        { week: 13, source: "Day062 교재1", ko: "공급망 문제가 있으니, 가격이 올라가는 건 당연하죠.", en: "There’s a supply chain issue, so no wonder prices are rising." },
        { week: 13, source: "Day062 교재1", ko: "재료가 기본적으로 버터, 밀가루, 설탕이군. 그래서 맛이 좋은 거구나.", en: "The ingredients are basically just butter, flour, and sugar. No wonder it tastes good." },
        { week: 13, source: "Day062 교재2", ko: "Gerry가 어젯밤에 사장이랑 소주 다섯 병 마셨다더라.", en: "I heard Gerry drank five bottles of soju with the boss last night." },
        { week: 13, source: "Day062 교재2", ko: "아, 그래서 아침에 그 친구 눈이 그렇게 빨갰구나.", en: "Oh, no wonder his eyes were so red this morning." },
        { week: 13, source: "Day062 교재2", ko: "간식 고마워요. 아침 먹고는 아무것도 못 먹었어요.", en: "Thank you for the snack. I didn’t have anything since breakfast." },
        { week: 13, source: "Day062 교재2", ko: "알죠! 그러면 당연히 배고프죠.", en: "I see! No wonder you were so hungry." },
        { week: 13, source: "Day062 교재2", ko: "들어 보니까 은행 직원들은 거의 밤 9시까지 야근을 해야 한대.", en: "I heard some bank workers pretty much have to stick around the office until 9 p.m." },
        { week: 13, source: "Day062 교재2", ko: "그래서 파업을 하는 거구나. 돈을 그렇게 많이 받는데 왜 파업을 하나 했거든.", en: "No wonder they’re on strike. I was wondering, since they get paid so much." },
        { week: 13, source: "Day062 교재3", ko: "타임스퀘어 근처 식당에서 산 이 햄버거 크기 좀 봐. 메뉴에서 봤을 때는 이렇게 큰 줄 몰랐어. 게다가 브레드 스틱도 같이 나오네. 이러니 미국 사람들이 과체중인 게 당연하지.", en: "Look at the size of this hamburger I got from a diner near Times Square. When I saw it on the menu, it didn’t look this big! And it comes with a side of breadsticks. No wonder Americans tend to be overweight." },
        { week: 13, source: "Day062 교재4", ko: "아침으로 시리얼을 먹은 거야? 좀 더 든든한 걸로 먹어야지.", en: "You just had cereal for breakfast? You should have something more substantial than that." },
        { week: 13, source: "Day062 교재4", ko: "아침을 거르는 경우가 대부분입니다.", en: "I skip breakfast, more often than not." },
        { week: 13, source: "Day062 교재4", ko: "오늘 나랑 점심 가볍게 할까?", en: "You wanna grab lunch with me today?" },
        { week: 13, source: "Day062 대표", ko: "어쩐지 기분이 상쾌해 보이더라.", en: "No wonder you look so refreshed." },
        { week: 13, source: "Day063 교재1", ko: "제 상황에 해당하는 딱 맞는 단어가 생각이 안 납니다.", en: "I can’t think of the right word for my situation." },
        { week: 13, source: "Day063 교재1", ko: "‘화가 나’보다 내 감정을 더 잘 표현할 수 있는 단어는 없는 듯해.", en: "I can’t think of a better word to describe how I feel than ‘angry’." },
        { week: 13, source: "Day063 교재1", ko: "전시회 너무 멋졌어. 오후 시간을 이보다 더 잘 보낼 수가 있을까?", en: "What a nice exhibition! I can’t think of a better way to spend my afternoon off." },
        { week: 13, source: "Day063 교재1", ko: "남은 치즈를 어디에다 써야 할지 모르겠네.", en: "I can’t think of a use for all this leftover cheese." },
        { week: 13, source: "Day063 교재1", ko: "듀얼 모니터 쓰면 너무 편리해. 동시에 여러 가지 작업을 하거나 작업을 바꿔 가며 하는 게 가능하거든. 단점은 찾을 수가 없어.", en: "Using dual monitors is really convenient. I can multitask or switch between tasks. I can’t think of any downside." },
        { week: 13, source: "Day063 교재2", ko: "아는 사람 중에 전기차 타는 사람 있어?", en: "Do you know anyone who has an electric vehicle?" },
        { week: 13, source: "Day063 교재2", ko: "당장은 생각나는 사람이 없는데 그래도 한 명은 있을 거야. 자동차 회사랑 딜러들 모두 전기차 홍보에 힘쓰고 있잖아.", en: "I can’t think of anyone at the moment, but I must know at least one. Car makers and dealers are all trying to promote electric vehicles." },
        { week: 13, source: "Day063 교재2", ko: "선생님, 한국어 ‘정’에 해당하는 좋은 번역은 뭘까요?", en: "Sir, what would be a good translation for the Korean term, ‘Jeong’?" },
        { week: 13, source: "Day063 교재2", ko: "네, 그 질문 진짜 많이 받았는데요. 저도 딱 한 단어로는 생각이 안 납니다. affection(애정)? attachment(애착)? 딱 이거다 싶은 게 하나도 없네요.", en: "Yeah, I’ve been getting that question a lot, but I can’t really think of a single good expression. Affection? Attachment? Nothing seems quite right." },
        { week: 13, source: "Day063 교재3", ko: "(사무용품 회사 직원이 같은 회사 타 부서 팀장에게 보내는 이메일)\n조 팀장님께\n잠깐 시간 되시면, 배송 문제 좀 도와주실 수 있을까요? 저희가 어쩌다가 며칠 동안 배송하는 걸 깜박했고요, 배송일을 약속한 것이 목요일인데 그때까지 고객에게 물건을 배송할 방법이 생각나지 않습니다.", en: "Mr. Cho,\nIf you have a moment, I could use your help with a shipping problem. We accidentally forgot to send a package out for several days, and now I can’t think of a way to get it to the customer by Thursday, which is our guaranteed delivery date." },
        { week: 13, source: "Day063 교재4", ko: "A: 이제 구인 공고 올리셨나요?", en: "Have you gotten around to posting that job opening yet?" },
        { week: 13, source: "Day063 교재4", ko: "B: 죄송해요. 정말 깜박했어요.", en: "Oh, I’m sorry. That slipped my mind." },
        { week: 13, source: "Day063 교재4", ko: "잘 기억이 안 나.", en: "I don’t quite remember." },
        { week: 13, source: "Day063 교재4", ko: "나 공과금 안 낸 거 이제 생각났네.", en: "It just occurred to me that I didn’t pay the bill." },
        { week: 13, source: "Day063 교재4", ko: "방금 든 생각인데요. 교사로 일할 때 학생들 대부분이 꿈은 없고 공부에만 전념했던 것 같네요.", en: "It just occurred to me that, when I worked as a teacher, most of my students didn’t have any dreams, and only focused on studying." },
        { week: 13, source: "Day063 대표", ko: "이 말을 어떻게 꺼내야 할지.", en: "I can’t think of the right thing to say." },
        { week: 13, source: "Day064 교재1", ko: "그래서 내가 다른 재즈 페스티벌에 안 가는 거야. 그나저나 넌 재즈 좋아해?", en: "That’s why I’ll never go to another Jazz Festival. Do you like jazz, by the way?" },
        { week: 13, source: "Day064 교재1", ko: "이 방에는 두 개의 트윈 침대가 구비되어 있습니다. 참고로 해변도 너무 잘 보입니다.", en: "The room comes with two twin beds. You’ll also have a great view of the beach, by the way." },
        { week: 13, source: "Day064 교재1", ko: "제 친구가 트레이너를 구하고 있어요. 참고로 제 친구는 싱글이에요.", en: "I have a friend who’s looking for a trainer. He’s single, by the way." },
        { week: 13, source: "Day064 교재1", ko: "Mark랑 Mindy 먹을 음식도 주문해야 해. 그나저나 그 친구들은 언제 도착한대?", en: "We’ll just have to order something for Mark and Mindy. When are they coming, by the way?" },
        { week: 13, source: "Day064 교재2", ko: "나랑 같이 요가 수업 받을래? 친구를 소개하면 할인받을 수 있거든.", en: "Do you want to join this yoga class with me? I can get a discount for referring a friend." },
        { week: 13, source: "Day064 교재2", ko: "생각해 볼게. 유연성을 좀 기르긴 해야 해. 근데 선생님 귀여우셔?", en: "I’ll think about it. I do need to work on my flexibility. By the way, is the instructor cute?" },
        { week: 13, source: "Day064 교재2", ko: "아직 만나는 사람 없지? 내 친구 Samantha 소개해 줄까? 네 또래인 데다 엄청 착해.", en: "You’re still single, right? Can I set you up with my friend, Samantha? She’s your age and really kind." },
        { week: 13, source: "Day064 교재2", ko: "좋아! 그나저나 Samantha MBTI가 뭔지 알아?", en: "Sounds great! By the way, do you know Samantha’s MBTI?" },
        { week: 13, source: "Day064 교재2", ko: "안녕하세요. 벤츠 신모델 정보 좀 알고 싶어서요.", en: "Hi there. I’d like some more information on the new Mercedes model." },
        { week: 13, source: "Day064 교재2", ko: "물론이죠. 전부 말씀드릴게요. 그나저나 지금 타는 차량 종류가 어떤 거세요?", en: "Sure, I can tell you all about it. Which make of car are you currently driving, by the way?" },
        { week: 13, source: "Day064 교재3", ko: "어젯밤에 나랑 놀아 줘서 고마워! 나는 너무 재미있었는데 너도 그랬으면 좋겠어. 그나저나 회사 안 늦었어? 너 택시 타다가 넘어질 뻔해서 좀 걱정되더라고.", en: "Thanks for hanging out with me last night! I had a great time and I hope you felt the same way. Btw, did you make it to work on time? I was a little worried after you almost fell getting into a cab." },
        { week: 13, source: "Day064 교재4", ko: "A: Greg, 비 오니?", en: "Is it raining, Greg?" },
        { week: 13, source: "Day064 교재4", ko: "B: 아니, 그래도 비옷 챙기렴. 비 올지도 모르잖아.", en: "No, but bring a raincoat anyway. It might rain." },
        { week: 13, source: "Day064 교재4", ko: "A: 어디로 2차를 가야 할지 모르겠네. 주변에 내가 제일 좋아하는 바는 벌써 영업이 끝났거든.", en: "I don’t know where a good place would be to keep drinking. My favorite bar around here is already closed." },
        { week: 13, source: "Day064 교재4", ko: "B: 사실, 괜찮아. 어차피 나 지금 집에 가서 자야 하거든.", en: "Actually, it’s okay. It’s about time for me to get home and go to bed anyway." },
        { week: 13, source: "Day064 교재4", ko: "파리 물가가 비싸긴 하지. 그래도 많은 사람들이 파리에서 휴가를 즐기고 싶어 해.", en: "Paris is expensive, but many people would like to vacation there, anyway." },
        { week: 13, source: "Day064 대표", ko: "새해가 코앞이네. 그나저나 너 부모님 댁에 갈 거야?", en: "New Year’s is just around the corner. Are you going to your parent’s house, by the way?" },
        { week: 13, source: "Day065 교재1", ko: "너 남대문 열린 거 아니?", en: "Are you aware your zipper is down?" },
        { week: 13, source: "Day065 교재1", ko: "너 이에 뭐 낀 거 알아?", en: "Are you aware there is something in your teeth?" },
        { week: 13, source: "Day065 교재1", ko: "이 좌석이 예약석인 줄을 몰랐습니다.", en: "I wasn’t aware that this table was reserved." },
        { week: 13, source: "Day065 교재1", ko: "너 아는지 모르겠는데, 화장실 세면대 막혔어.", en: "I don’t know if you’re aware of this, but the bathroom sink is clogged." },
        { week: 13, source: "Day065 교재1", ko: "네가 아는지 모르겠지만, 수지 동생이 많이 아파.", en: "I don’t know if you’re aware of it, but Suzie’s brother has been seriously ill." },
        { week: 13, source: "Day065 교재2", ko: "셔츠 주머니에 얼룩 묻은 거 아세요?", en: "Are you aware that you have a stain on your shirt pocket?" },
        { week: 13, source: "Day065 교재2", ko: "네, 알고 있는데 지금은 어떻게 할 수가 없어요. 여분 셔츠를 사무실에 하나 둬야겠군요.", en: "Yeah, I know, but there’s nothing I can do about it right now. I think I should keep an extra shirt in my office." },
        { week: 13, source: "Day065 교재2", ko: "김 군과의 면접은 생각보다 별로였어.", en: "I wasn’t very impressed with Mr. Kim’s interview." },
        { week: 13, source: "Day065 교재2", ko: "진짜로? 그 친구 배경을 모르나 보네? 해외 유학도 간 적이 없거든.", en: "Oh, really? Aren’t you aware of his background? He’s never studied abroad." },
        { week: 13, source: "Day065 교재2", ko: "저 사실 남자 친구랑 왔는데요.", en: "I’m actually here with my boyfriend." },
        { week: 13, source: "Day065 교재2", ko: "아, 죄송합니다. 일행이 있는 줄은 몰랐네요.", en: "Oh, I’m sorry. I wasn’t aware you were with someone." },
        { week: 13, source: "Day065 교재3", ko: "안녕하세요, 고객님,\n혹시 모르고 계실까 봐 말씀드리자면, 고객님이 선결제한 데이터를 다 쓰셨습니다. 추가 데이터를 구매하기 바랍니다. 그렇지 않으면 10일 자정부터 서비스가 중단됩니다.\nGT 고객 서비스", en: "Dear customer,\nIn case you aren’t aware, you have used up all of your pre-paid data. Please purchase additional data credit. Otherwise, your service will be suspended starting at midnight on the 10th.\nGT Customer Service" },
        { week: 13, source: "Day065 교재4", ko: "지퍼가 열렸네.", en: "Your fly is open." },
        { week: 13, source: "Day065 교재4", ko: "내가 너를 잃는 것 같은 느낌이 들어.", en: "I feel like I’m losing you." },
        { week: 13, source: "Day065 대표", ko: "시간 가는 줄도 몰랐네.", en: "I wasn’t aware of the time." },

        // Week 14
        { week: 14, source: "Day066 교재1", ko: "(그룹 콜(단체 통화) 상황에서) 이제 전화를 끊어야 할 듯하네요.", en: "I’m afraid we’ll have to let you go." },
        { week: 14, source: "Day066 교재1", ko: "벌써 밤 11시네. 전화 끊어야겠다.", en: "It’s already 11 p.m. I think I will have to let you go." },
        { week: 14, source: "Day066 교재1", ko: "전화 끊어야 할 듯해. 나 버스 타거든.", en: "I think I will have to let you go. I’m getting on the bus." },
        { week: 14, source: "Day066 교재1", ko: "전화 끊어야겠다. 다른 전화가 들어와서.", en: "I’ll have to let you go. I’m getting another call." },
        { week: 14, source: "Day066 교재1", ko: "(줌 회의 중에) 이 회의 바로 다음에 다른 회의가 잡혀 있어서, 죄송하지만 여기서 마쳐야 할 것 같습니다.", en: "I have another meeting scheduled right after this, so I’m afraid I’ll have to let you go." },
        { week: 14, source: "Day066 교재2", ko: "음, 엄마, 전화 끊어도 될까요? 출근 준비를 해야 해서요.", en: "Well, Mom, is it alright if I let you go? I should start getting ready for work." },
        { week: 14, source: "Day066 교재2", ko: "당연하지, 얘야. 전화 고마워. 회사에서 좋은 하루 보내고.", en: "Of course, Honey! Thanks for calling. Have a great day at work." },
        { week: 14, source: "Day066 교재2", ko: "미안한데, 전화가 또 들어오네. 잠깐 끊어도 될까?", en: "Sorry, I’m getting another call. Can I let you go for now?" },
        { week: 14, source: "Day066 교재2", ko: "응. 통화 끝나면 바로 다시 전화 줘.", en: "Okay, but please call me back right away when you’re done." },
        { week: 14, source: "Day066 교재2", ko: "비번 리셋을 했는데도 여전히 이메일 접속이 안 됩니다.", en: "Even after I reset my password, I still can’t get into my email account." },
        { week: 14, source: "Day066 교재2", ko: "알겠습니다, 신 과장님. 해결책 찾는 데 시간이 좀 걸릴 것 같으니 지금은 전화 끊고 방법 찾으면 제가 다시 전화드리는 게 어떨까요?", en: "Okay, Ms. Shin. It’s probably going to take me some time to figure out a solution, so how about I let you go and then call you back when I’m done?" },
        { week: 14, source: "Day066 교재3", ko: "(마이애미에 거주하는 미국인 부모님이 서울에 사는 딸에게 하는 톡 대화 중)\n시간이 많이 늦었으니 들어가 봐. 우리가 곧 서울 가니까! 마이애미에서 뭐 사 오라고 할 것 있으면, 우리 비행기 타기 전에 문자 주렴.", en: "It’s getting pretty late here, so I will have to let you go. We’ll be there in Seoul before you know it, though! Text me before the flight if you need anything from Miami." },
        { week: 14, source: "Day066 교재4", ko: "나 아직 사무실이야. 아무래도 오늘은 못 갈 거 같아.", en: "I’m still in the office. I don’t think I can make it today." },
        { week: 14, source: "Day066 교재4", ko: "접속 장애로 인해 오전 내내 폴더에 접속을 할 수가 없네요.", en: "Due to connection issues, I’ve been unable to get into the folder all morning." },
        { week: 14, source: "Day066 교재4", ko: "제 네이버 계정에 접속이 안 되는데 왜 그런지 모르겠어요.", en: "I can’t get into my Naver account, but I don’t know why." },
        { week: 14, source: "Day066 대표", ko: "이제 그만 들어가 보렴.", en: "I think I will have to let you go." },
        { week: 14, source: "Day067 교재1", ko: "한 정거장만 더 가면 돼. 곧 도착해!", en: "I’m only one stop away. I’ll be there soon!" },
        { week: 14, source: "Day067 교재1", ko: "주말이 이틀밖에 안 남았는데, 아직 계획이 없어. 나랑 서울 숲 근처에서 뭐 할래?", en: "The weekend is only two days away, but I don’t have any plans yet. Do you want to do something with me around Seoul Forest?" },
        { week: 14, source: "Day067 교재1", ko: "여자 친구 생일이 일주일밖에 안 남았다니. 뭘 해 줘야 할지 모르겠어.", en: "I can’t believe my girlfriend’s birthday is only a week away. I still don’t know what to get her." },
        { week: 14, source: "Day067 교재1", ko: "밸런타인데이가 며칠 안 남았네. 아내를 놀라게 해 주고 싶은데, 뭐가 제일 좋을지 고민이야.", en: "Valentine’s Day is only a few days away. I want to surprise my wife, but I still can’t figure out what would be best." },
        { week: 14, source: "Day067 교재2", ko: "기말시험이 2주밖에 안 남았어. 나 진짜 제대로 공부 시작해야 할 것 같아.", en: "My finals are only two weeks away. I’m afraid I need to really get down to studying." },
        { week: 14, source: "Day067 교재2", ko: "아, 그럼 시험 끝날 때 까지는 못 논다는 거지?", en: "Ah, so you won’t be able to hang out until after?" },
        { week: 14, source: "Day067 교재2", ko: "아내 생일이 일주일밖에 안 남았어. 그런데 뭘 사 줘야 할지 고민이야", en: "My wife’s birthday is only a week away, but I can’t figure out what to get her." },
        { week: 14, source: "Day067 교재2", ko: "있잖아, 나 지난달에 여자 친구에게 멋진 팔찌를 사 줬거든. 그 보석 브랜드 홈페이지 알려 줄게.", en: "You know, I got my girlfriend a nice bracelet last month. I’ll share the jeweler’s website with you." },
        { week: 14, source: "Day067 교재2", ko: "출간일이 한 달밖에 안 남았어요. 그런데 아직 80%도 못 끝냈어요.", en: "The release date is a month away, but I’m not even 80% finished." },
        { week: 14, source: "Day067 교재2", ko: "아, 정말요? 검수, 편집에 조판도 해야 하잖아요. 출간일을 늦추는 것도 진지하게 생각해 봐야겠네요.", en: "Oh, really? We still need to proofread, edit, and typeset. We should strongly consider pushing the date back." },
        { week: 14, source: "Day067 교재3", ko: "제품 발매일이 일주일도 안 남았고 저희 SNS가 난리가 났습니다. 각 지점에서는 충분한 물량을 확보해 주시기를 바라며, 분주한 시기를 관리하기 위해 임시직 직원을 채용하는 것도 생각해 보아야 할 것 같습니다.", en: "The launch is less than a week away, and we’re seeing a lot of excitement on our social media. I want to make sure each branch has plenty of stock. Also, we should consider hiring seasonal workers to manage the rush." },
        { week: 14, source: "Day067 교재4", ko: "저 학위 마치기까지 한 학기밖에 안 남았어요.", en: "I’m only one semester away from finishing my degree." },
        { week: 14, source: "Day067 교재4", ko: "이제 8년만 있으면 연금을 받습니다.", en: "I’m only eight years away from getting my pension." },
        { week: 14, source: "Day067 교재4", ko: "콘서트 시작까지 2시간밖에 안 남았어요.", en: "We’re only two hours away from the concert getting started." },
        { week: 14, source: "Day067 교재4", ko: "이 책 끝내는 데 딱 33일 남았어!", en: "I am only 33 days away from finishing this book!" },
        { week: 14, source: "Day067 대표", ko: "설이 일주일도 채 안 남았네.", en: "Lunar New Year is less than a week away." },
        { week: 14, source: "Day068 교재1", ko: "(공사가 지연되는 상황에서) 3개월 지연되고 있는 상태입니다.", en: "I’m afraid we are three months behind schedule." },
        { week: 14, source: "Day068 교재1", ko: "<이상한 변호사 우영우> 보고 있는데 한 3, 4화 정도 밀렸거든. 그러니까 줄거리 미리 말해서 초 치지 마.", en: "I’ve been watching Extraordinary Attorney Woo, but I’m, like, three or four episodes behind. Please don’t spoil anything." },
        { week: 14, source: "Day068 교재1", ko: "공과금이 한 번 밀리기 시작하면, 계속 밀리게 돼.", en: "Once you get behind on your bills, it can be difficult to catch up." },
        { week: 14, source: "Day068 교재1", ko: "나 숙제가 좀 밀렸어. 주말 내내 못 한 숙제를 해야 해.", en: "I’m pretty behind on homework. I’ll have to spend all weekend catching up." },
        { week: 14, source: "Day068 교재2", ko: "이런! 이번 달 전기료 좀 봐. 통장에 돈이 충분히 있는지 모르겠네.", en: "Oh man! Look at this month’s electricity bill. I’m not sure I have enough money in my checking account." },
        { week: 14, source: "Day068 교재2", ko: "우리 이미 한 달 밀렸어. 또 밀리면 전기 끊겨.", en: "You know, we’re already one month behind on payment. If we’re late again, they’re going to cut us off." },
        { week: 14, source: "Day068 교재2", ko: "안녕하세요, 수진 씨! 공부는 잘돼요? 월세 곧 입금할 건지 알고 싶어서요. 한 달 치가 밀렸거든요.", en: "Hi, Sujin! Are your studies going okay? I just wanted to ask if you’re going to transfer the rent soon. You’re one month behind on it." },
        { week: 14, source: "Day068 교재2", ko: "이런! 죄송해요. 과제를 하느라 완전히 깜박했네요.", en: "Oh my gosh! I’m so sorry. I’ve been working on some projects, and it totally slipped my mind." },
        { week: 14, source: "Day068 교재2", ko: "우리가 국세청에 소득 신고를 해야 하는지 몰랐어.", en: "I didn’t realize that we had to report our earnings to the tax office." },
        { week: 14, source: "Day068 교재2", ko: "이런! 그럼, 몇 달 정도 밀렸겠는데.", en: "Oh, no! We must be, like, a few months behind." },
        { week: 14, source: "Day068 교재3", ko: "(원어민 선생님이 과외를 받는 학생에게 보내는 메시지)\n수연 님, 제가 은행 거래내역을 확인하고 있었는데, 보니까 지난 수업료 입금한 지가 꽤 됐더라고요. 6월 23일에 입금된 것 같은데, 그럼 두 달 치 수업료가 밀린 것 같아요. 맞을까요?", en: "Sooyeon, I was just going through my bank transactions, and I found that it has been a while since your last tuition payment. I think that was on June 23rd, which would mean you’re nearly two months behind on tuition. Does that look right to you?" },
        { week: 14, source: "Day068 교재4", ko: "나 지금 터널 통과 중이야.", en: "I am going through a tunnel." },
        { week: 14, source: "Day068 교재4", ko: "요즘 Sally가 여러 가지로 힘들어.", en: "Sally is going through a lot lately." },
        { week: 14, source: "Day068 교재4", ko: "옷장을 샅샅이 뒤져 봤는데도, 결혼식에 뭐 입고 갈지를 모르겠네요.", en: "I went through my whole closet, but I can’t figure out what to wear for the wedding." },
        { week: 14, source: "Day068 대표", ko: "일이 밀려서 점심 먹을 시간도 없어.", en: "I don’t have time to grab lunch. I’m behind on work." },
        { week: 14, source: "Day069 교재1", ko: "A: 매출이 살아나고 있습니다.", en: "A: Sales are picking up." },
        { week: 14, source: "Day069 교재1", ko: "B: 확실히 말이죠.", en: "B: That’s for sure." },
        { week: 14, source: "Day069 교재1", ko: "A: 정치인들은 다 거짓말쟁이야.", en: "A: Politicians are all liars." },
        { week: 14, source: "Day069 교재1", ko: "B: 그건 확실해.", en: "B: That’s for sure." },
        { week: 14, source: "Day069 교재1", ko: "A: 우리는 이와 같은 무역 전쟁을 계속해서는 안 됩니다.", en: "A: We can’t afford to continue this trade war." },
        { week: 14, source: "Day069 교재1", ko: "B: 그 점은 분명합니다.", en: "B: That’s for sure." },
        { week: 14, source: "Day069 교재1", ko: "A: 제 남편이 바람을 피울 사람은 아니에요.", en: "A: My husband is not the kind of guy who would ever cheat." },
        { week: 14, source: "Day069 교재1", ko: "B: 그건 확실해요.", en: "B: That’s for sure." },
        { week: 14, source: "Day069 교재1", ko: "A: Jonathan은 그 정도 스펙이면 다른 직장 구하는 데 문제 없을 거야.", en: "A: Jonathan won’t have any trouble getting another job with his qualifications." },
        { week: 14, source: "Day069 교재1", ko: "B: 내 말이.", en: "B: That’s for sure." },
        { week: 14, source: "Day069 교재2", ko: "그 사람 좀 고집불통인 것 같아.", en: "I just thought he was a little stubborn." },
        { week: 14, source: "Day069 교재2", ko: "내 말이.", en: "That’s for sure." },
        { week: 14, source: "Day069 교재2", ko: "요즘은 몇몇 대기업이 우리 삶을 지배하고 있어요. 우리가 네이버와 카카오에 너무 의존하는 것 같아요.", en: "Our lives are kind of dominated now by a few huge conglomerates. I feel like we rely too much on Naver and KakaoTalk." },
        { week: 14, source: "Day069 교재2", ko: "너무 맞는 말씀입니다. 반드시 우리나라를 스타트업에게 더 환영받을 수 있는 곳으로 만들어야 해요.", en: "That’s for sure. We should definitely make Korea a more welcoming place for startups." },
        { week: 14, source: "Day069 교재2", ko: "우리 이번 프로젝트 진짜 열심히 했어요. 끝나면 연봉 인상을 요구합시다.", en: "We’ve worked so hard on this project. We should ask for a raise once it’s over." },
        { week: 14, source: "Day069 교재2", ko: "당연히 그래야죠. 우리의 가치를 이미 증명했으니까요.", en: "That’s for sure. We’ve proven our worth." },
        { week: 14, source: "Day069 교재3", ko: "George는 최고의 인사부 관리자입니다. 입사 후 30년간 적어도 신규 직원 절반을 교육한 사람이죠. 우리가 성장한 것도 이분의 공이 큽니다. 의심의 여지가 없지요!", en: "George has been a terrific human resources manager. Since he joined 30 years ago, he has helped train at least half of all new hires. Much of our growth was only possible thanks to him. That’s for sure!" },
        { week: 14, source: "Day069 교재4", ko: "전적으로 동의합니다.", en: "I couldn’t agree with you more." },
        { week: 14, source: "Day069 교재4", ko: "제 말이요. (상대의 말에 맞장구 치는 말)", en: "You can say that again." },
        { week: 14, source: "Day069 교재4", ko: "그 점에 있어서는 동의하기 힘듭니다.", en: "I can’t agree with you on that." },
        { week: 14, source: "Day069 대표", ko: "누가 아니래.", en: "That’s for sure." },
        { week: 14, source: "Day070 교재1", ko: "블랙과 화이트의 컬러 조합은 잘못될 수가 없습니다.", en: "You can’t go wrong with the color combination of black and white." },
        { week: 14, source: "Day070 교재1", ko: "어두운 회색 슈트는 언제나 옳지.", en: "You can’t go wrong with a dark gray suit." },
        { week: 14, source: "Day070 교재1", ko: "날씨 좋은 곳 원하면, 무조건 샌디에이고가 답이다.", en: "If you want good weather, you can’t go wrong with San Diego." },
        { week: 14, source: "Day070 교재1", ko: "감자와 치즈는 언제나 옳다.", en: "Potatoes and cheese. You can’t go wrong with them." },
        { week: 14, source: "Day070 교재1", ko: "BMW는 언제나 옳은 선택이지.", en: "You can never go wrong with BMW." },
        { week: 14, source: "Day070 교재2", ko: "나도 하루 종일 아무것도 못 먹었어. 넌 뭐 먹고 싶어?", en: "I haven’t eaten all day, either. What do you want?" },
        { week: 14, source: "Day070 교재2", ko: "난 고기가 너무 당기는데 한국식 바비큐는 언제나 옳지.", en: "I’m craving meat, and we can’t go wrong with Korean BBQ." },
        { week: 14, source: "Day070 교재2", ko: "20명이 오는데, 아마도 피자 다섯 판이면 충분할 듯. 무슨 피자 시켜야 할까?", en: "We have 20 people coming, so maybe five pizzas will be enough. What should we get?" },
        { week: 14, source: "Day070 교재2", ko: "치즈 페퍼로니 시키면 실패할 일이 없지.", en: "You can’t go wrong with just cheese and pepperoni." },
        { week: 14, source: "Day070 교재2", ko: "엄마. 이 의상 어때요? 회사 갈 때 입기에는 조금 그런 것 같기도 하고.", en: "Mom, what do you think of this outfit? I’m not sure if it’s really appropriate for work." },
        { week: 14, source: "Day070 교재2", ko: "한번 보자. 바지가 좀 타이트하네. 근데 상의를 블레이즈를 입었으니 괜찮을 것 같다. 그 두 조합은 언제나 옳거든.", en: "Let me see. The pants are a little tight, but you’ve got the blazer on top, which makes it alright. You can’t go wrong with that combination." },
        { week: 14, source: "Day070 교재3", ko: "어디에 투자해야 할지를 두고 아직도 고민 중이십니까? 지난 몇 년간 온갖 스타트업에 다 투자해 본 후 내린 결론은 바이오 스타트업이 가장 안전한 선택이라는 점입니다. 바이오는 실패할 일이 없다는 것이 제 생각입니다.", en: "Are you still trying to figure out where to invest your money? Having invested in all sorts of start-ups over the years, I have found that bio-startups are the safest option. In my opinion, it’s hard to go wrong with them." },
        { week: 14, source: "Day070 교재4", ko: "보통은 역까지 2~3분밖에 안 걸리는데, 항상 최소 6분은 일찍 집을 나섭니다. 혹시 모르니까 말이죠.", en: "It usually only takes two or three minutes to get to the station, but I always try to leave my place at least six minutes early, to be safe." },
        { week: 14, source: "Day070 교재4", ko: "아침에 눈이 온다더라. 혹시 모르니 버스보다는 지하철 타는 게 나을 것 같아.", en: "I heard it will snow in the morning. It might be better to take the subway rather than the bus, just to be safe." },
        { week: 14, source: "Day070 교재4", ko: "고수가 오천 원 정도 한다던데. 그래도 혹시 모르니 만 원 가져가 보려고.", en: "I heard cilantro is around 5,000 won. I’ll bring 10,000 won to be safe." },
        { week: 14, source: "Day070 대표", ko: "검은색이 진리지.", en: "You can’t go wrong with black." },

        // Week 15
        { week: 15, source: "Day071 교재1", ko: "저녁 먹고 갈래?", en: "Can you stay for dinner?" },
        { week: 15, source: "Day071 교재1", ko: "저 사실 이케아에 가구 보러 다녀왔어요.", en: "I actually went shopping for furniture at IKEA." },
        { week: 15, source: "Day071 교재1", ko: "나가서 잠시 바람 좀 쐬어도 될까요?", en: "Can I go out just a couple of minutes for some fresh air?" },
        { week: 15, source: "Day071 교재1", ko: "나 면접이 있어서 먼저 일어나 봐야 할 것 같아.", en: "I’m afraid I’ll have to leave early for an interview." },
        { week: 15, source: "Day071 교재1", ko: "내일 아침에 건강 검진이 있어서 저녁 8시부터 금식해야 해요.", en: "I have to fast, starting at 8 p.m., for my check-up tomorrow morning." },
        { week: 15, source: "Day071 교재2", ko: "나 이번 주말에 아이엘츠 시험 봐. 최소 6점은 받았으면 좋겠는데.", en: "I’m taking the IELTS this weekend, and I hope to get at least a 6." },
        { week: 15, source: "Day071 교재2", ko: "아, 승진 때문에 그게 필요한 거야?", en: "Oh, do you need that for a promotion?" },
        { week: 15, source: "Day071 교재2", ko: "저희 아버지는 더 나은 삶을 위해 미국으로 이주하셨지만, 결국 이곳 공장에서 일하게 되셨지요.", en: "My father moved to America for a better life, but he ended up working in factories here, too." },
        { week: 15, source: "Day071 교재2", ko: "대부분 그렇죠. 특히 동남아시아인들의 경우 말이죠.", en: "That happens way too often, especially with Southeast Asians." },
        { week: 15, source: "Day071 교재2", ko: "여자 친구 주려고 카시오 시계 브랜드인 G-Shock 보고 왔어.", en: "I went shopping for G-Shock for my girlfriend." },
        { week: 15, source: "Day071 교재2", ko: "여자 친구가 정말 좋아할 만한 선물일까?", en: "Is that really the kind of gift she enjoys?" },
        { week: 15, source: "Day071 교재3", ko: "(우체국에서 빠른 배송을 원하는 고객에게 직원이 하는 말)\n택배가 이번 주에 도착하기를 원하는 것은 이해하지만 그러려면 항공 우편밖에 방법이 없습니다. 신속 배송을 하려면 요금을 두 배로 내셔야 하는데, 정말 그렇게 하시겠어요?", en: "I understand that you want your package to arrive this week, but I’m afraid the only other option is via airmail, and you would have to pay twice as much for expedited shipping. Are you sure you’d like to go ahead with that?" },
        { week: 15, source: "Day071 교재4", ko: "디자인 때문에 아이폰으로 선택했어요.", en: "I chose the iPhone for its design." },
        { week: 15, source: "Day071 교재4", ko: "그 여자는 그 남자 돈 보고 만나는 거야?", en: "Is she with him for his money?" },
        { week: 15, source: "Day071 교재4", ko: "그는 지각해서 혼났다.", en: "He got told off for coming in late." },
        { week: 15, source: "Day071 교재4", ko: "그 집 리모델링한다고 영업을 안 해.", en: "They are closed for remodeling." },
        { week: 15, source: "Day071 대표", ko: "나가서 바람이나 좀 쐬고 오자.", en: "Let’s go out for some fresh air." },
        { week: 15, source: "Day072 교재1", ko: "너 만나서 저녁 먹으니 좋긴 한데 너무 갑작스럽게 연락했네. 어떤 일 때문에 보자고 한 거니?", en: "I’m happy to meet you for dinner, but you kind of called me out of the blue. What is this about?" },
        { week: 15, source: "Day072 교재1", ko: "Sally가 문자에 답이 없네. 너 혹시 Sally가 왜 그러는지 아니?", en: "Sally isn’t responding to my texts. Do you know what that’s about?" },
        { week: 15, source: "Day072 교재1", ko: "보니까 우리 이따가 회의가 하나 더 잡혀 있군요. 어떤 내용일까요?", en: "I see we have another meeting scheduled later. What is it about?" },
        { week: 15, source: "Day072 교재1", ko: "혹시 어떤 일 때문에 그러시는지 여쭤봐도 될까요?", en: "May I ask what this is about?" },
        { week: 15, source: "Day072 교재2", ko: "Jeff 씨와 통화할 수 있을까요?", en: "I’d like to speak to Jeff please." },
        { week: 15, source: "Day072 교재2", ko: "어떤 일 때문이신지 여쭤봐도 될까요?", en: "May I ask what this is about?" },
        { week: 15, source: "Day072 교재2", ko: "문 닫고 들어오실래요?", en: "Please close the door behind you." },
        { week: 15, source: "Day072 교재2", ko: "아, 무슨 일 때문에 그러시는데요? 제가 지각을 한 것 때문일까요?", en: "Oh, no. What is this about? Is this about me showing up late?" },
        { week: 15, source: "Day072 교재2", ko: "부모님이 이번 금요일에 남산에 있는 그 프랑스 식당에서 저녁 먹자고 초대하셨어.", en: "My parents invited us to that French restaurant on Namsan for dinner this Friday." },
        { week: 15, source: "Day072 교재2", ko: "정말? 조금 갑작스럽네. 무슨 일이시래? 뭐 중요한 말씀 하실 거 있대?", en: "Oh, really? It’s a little sudden. What is it about? Do they want to tell us something serious?" },
        { week: 15, source: "Day072 교재3", ko: "안녕, Jeff. 지난주에 서울에서 보게 돼서 좋았어. 기분 좋게 방문했기를 바라는데, 실은 그것 때문에 연락해 본 거야. 너 약간 불편해했던 것 같아서. 특히 고객사 사람들과 저녁 식사할 때 말이야. 혹시 뭐 때문에 그랬는지 물어봐도 될까? 그쪽 사람들 질문이 너무 사적인 것이었니?", en: "Hi Jeff, it was great seeing you in Seoul last week. I hope you had a nice visit, and actually, that’s why I’m writing. You seemed a little bit uncomfortable, especially at our dinner with the clients. Can I ask what that was about? Were the representatives’ questions perhaps too personal for you?" },
        { week: 15, source: "Day072 교재4", ko: "James랑 일하는 게 쉽지가 않더군요.", en: "It was tough working with James." },
        { week: 15, source: "Day072 교재4", ko: "그동안 함께 일할 수 있어서 너무 좋았습니다. 앞으로 성공만이 깃들길 기원합니다.", en: "It was a great pleasure working with you. I wish you nothing but success in the future." },
        { week: 15, source: "Day072 교재4", ko: "스코틀랜드 사람들 말은 늘 이해하기 어려웠어. 그래서 자막 없이 이번 영화를 보는 게 너무 힘들더라.", en: "I’ve always had trouble understanding Scottish people, so it was tough watching the movie with no subtitles." },
        { week: 15, source: "Day072 교재4", ko: "계단으로 드레서를 옮기는 게 진짜 힘들더군요.", en: "It was a real struggle getting the dresser up all those stairs." },
        { week: 15, source: "Day072 대표", ko: "무슨 일이신가요? 제 검사 결과 관련된 건가요?", en: "What is this about? Is this about my test results?" },
        { week: 15, source: "Day073 교재1", ko: "그 여자분 텍사스 사람 같더라.", en: "She sounded like a Texan." },
        { week: 15, source: "Day073 교재1", ko: "들어 보니까 그 사람 최고의 남자 친구네.", en: "He sounds like a perfect boyfriend." },
        { week: 15, source: "Day073 교재1", ko: "이 후기들 보니까 퇴근 후에 가서 시간 보내기 좋은 곳인 듯.", en: "These reviews make it sound like a chill place to hang out after work." },
        { week: 15, source: "Day073 교재1", ko: "말하는 거 들어 보니 우리랑 캠핑 갈 생각이 별로 없는 것 같군.", en: "You don’t sound like you are really interested in joining us for camping." },
        { week: 15, source: "Day073 교재1", ko: "진짜 제대로 된 바비큐를 못 먹어 본 모양이군.", en: "It sounds like you haven’t really tried authentic barbecue." },
        { week: 15, source: "Day073 교재2", ko: "이번 겨울에 샌디에이고에 갈까 하는데. 어떻게 생각해?", en: "I’m thinking of visiting San Diego this winter. What do you think?" },
        { week: 15, source: "Day073 교재2", ko: "일 년 내내 날씨가 온화하다고 하니 너에겐 딱 맞는 듯해.", en: "I heard they have mild weather all year round, so that sounds like a perfect place for you." },
        { week: 15, source: "Day073 교재2", ko: "그래. 필요하면 내가 워크숍 따라갈게.", en: "Okay, I am willing to come with you to the workshop, if you think I should." },
        { week: 15, source: "Day073 교재2", ko: "하하, 보니까 별로 안 가고 싶어 하는 것 같네. 강요는 안 해.", en: "Haha, it sounds like you really don’t want to go. I won’t force you." },
        { week: 15, source: "Day073 교재2", ko: "사무실 지나가는데 Randy가 통화하고 있었고, 단단히 화가 난 것 같던데. 왜 그러는지 알아?", en: "Randy was on the phone when I walked past his office, and he sounded like he was upset. Do you know what that was about?" },
        { week: 15, source: "Day073 교재2", ko: "응. 본사에서 중국으로 발령 내고 싶어 해서.", en: "Yeah. I think headquarters wants to transfer him to China." },
        { week: 15, source: "Day073 교재3", ko: "서울 주택 가격이 하락하면서 젊은이들은 안도의 한숨을 내쉬고 있습니다. 별일 아닌 듯 보일 수 있지만, 이는 다른 여러 문제로 이어질 수 있습니다. 많은 주택 보유자들이 버블 당시에 집을 구매해서 현재 많은 빚을 안고 있습니다. 대출을 많이 받은 것인데, 금리가 오르고 있기 때문에 상당한 부담을 느끼고 있습니다.", en: "Housing prices are falling in Korea’s capital, leaving young people breathing sighs of relief. And while this may not sound like an issue, it could lead to other problems. Many current homeowners are in debt after buying during the bubble. They took out huge loans, and with interest rates rising, they are feeling the squeeze." },
        { week: 15, source: "Day073 교재4", ko: "너 힘이 없어 보인다.", en: "You look low on energy." },
        { week: 15, source: "Day073 교재4", ko: "그 셔츠 입지 마. 범생 같아 보이잖아.", en: "You shouldn’t wear that shirt. It makes you look like a nerd." },
        { week: 15, source: "Day073 교재4", ko: "보니까 저 여성분 성형한 듯.", en: "She looks like she got some work done." },
        { week: 15, source: "Day073 교재4", ko: "보니까 너 머리 엄청 신경 쓰나 보다. 아침마다 머리 만지는 데 얼마나 걸리는지 궁금하네.", en: "It looks like you are very particular about your hair. I wonder how long it takes you to fix it every morning." },
        { week: 15, source: "Day073 대표", ko: "그게 훨씬 더 낫겠다.", en: "That sounds like an even better plan to me." },
        { week: 15, source: "Day074 교재1", ko: "제가 뭐 운전을 잘 못하는 것도 아닌데요.", en: "It’s not like I’m a bad driver or anything." },
        { week: 15, source: "Day074 교재1", ko: "내가 늘 패스트푸드를 먹는 것도 아닌데.", en: "It’s not like I eat fast food all the time." },
        { week: 15, source: "Day074 교재1", ko: "우리 가스 요금이 너무 많이 나왔더라, 근데 괜찮아. 감당하기 힘든 수준까지는 아니니.", en: "Our gas bill was really high, but it’s okay. It’s not like we can’t afford it." },
        { week: 15, source: "Day074 교재1", ko: "직장을 잃는 게 아니잖아. 그냥 전근 가는 거잖아.", en: "It’s not like you’re losing your job. It’s just a transfer." },
        { week: 15, source: "Day074 교재1", ko: "제가 무슨 욕을 했나요? 뭘 그걸 가지고 그러시죠?", en: "It’s not like I swore at you. What’s the big deal?" },
        { week: 15, source: "Day074 교재2", ko: "부인까지 두 분 다 스포츠카가 있다니 대단해요. 어떻게 감당하세요?", en: "I can’t believe you and your wife each have sports cars. How can you afford them?" },
        { week: 15, source: "Day074 교재2", ko: "뭐, 제가 부자는 아니고요. 그냥 둘 다 차를 정말 좋아해서요.", en: "Well, it’s not like I’m rich. It’s just that we’re both really into cars." },
        { week: 15, source: "Day074 교재2", ko: "내가 컵밥은 몸에 별로 안 좋다고 하지 않았나?", en: "Haven’t I told you that cupbop is really unhealthy?" },
        { week: 15, source: "Day074 교재2", ko: "알아요, 엄마. 근데 제가 맨날 패스트푸드를 먹는 것도 아니잖아요. 오늘은 밥을 해 먹기에 너무 피곤하더라고요.", en: "I know, Mom. It’s not like I eat fast food all the time. I was just too tired today to cook." },
        { week: 15, source: "Day074 교재2", ko: "보니까 너 예진이가 파티 오는 거 싫은가 보다.", en: "It seems like you don’t really want Yejin to come to the party." },
        { week: 15, source: "Day074 교재2", ko: "응, 안 불렀어. 뭐 안 좋은 감정이 있는 건 아니고. 술 취하면 남자들한테 집적대는 나쁜 버릇이 있어서.", en: "Yeah, I didn’t invite her. But it’s not like I have anything against her. She just has this bad habit of hitting on guys when she’s drunk." },
        { week: 15, source: "Day074 교재3", ko: "넷플릭스 드라마 시청을 강력 추천합니다. 그렇다고 제가 <하우스 오브 카드>나 <슈츠>를 엄청 좋아하는 것은 아닙니다. 처음에는 재미가 안 붙더군요. 당연히 습관이 되게 하려면 시간이 좀 걸리지만, 이보다 더 좋은 언어 학습 도구가 없지요.", en: "I strongly recommend watching Netflix shows, but it’s not like I’m a huge fan of House of Cards or Suits. I couldn’t really get into them at first. Of course, it takes quite some time to make it a habit, but I can’t think of a better language learning tool." },
        { week: 15, source: "Day074 교재4", ko: "민수가 연남동에 있는 바에서 어떤 미국 여자에게 작업을 걸고 있는 걸 봤어.", en: "I saw Minsu hitting on some American girl at a bar in Yeonnam-dong." },
        { week: 15, source: "Day074 교재4", ko: "지난 세 명의 여자 친구들과 헤어져서인지, 이제 한 명에게 집중을 못 할 것 같은 기분이 드네요.", en: "After my last three girlfriends broke up with me, I feel like I have some commitment issues." },
        { week: 15, source: "Day074 교재4", ko: "Tom이랑 저는 사실 진지하게 만나고 있습니다.", en: "Tom and I are actually in a serious relationship." },
        { week: 15, source: "Day074 교재4", ko: "보니까 그 친구 가볍게 만날 사람을 찾는 듯해.", en: "It seems like he is just looking for a casual relationship." },
        { week: 15, source: "Day074 대표", ko: "저희가 뭐 진지하게 사귀고 그런 건 아니에요.", en: "It’s not like we are in a serious relationship or anything." },
        { week: 15, source: "Day075 교재1", ko: "저녁 사 줘서 고마워! 근데 진짜 우리 집 가서 커피 안 하려고?", en: "Thank you for dinner! Are you sure you don’t want to come up for coffee?" },
        { week: 15, source: "Day075 교재1", ko: "진짜 우리랑 같이 저녁 안 하려고? 지난번에도 사장님 제안 거절했잖아!", en: "Are you sure you’re not going to join us for dinner? You turned down the boss last time, too!" },
        { week: 15, source: "Day075 교재1", ko: "내 여자 친구의 친구랑 진짜 소개팅 안 할 거야?", en: "Are you sure you don’t want to go on a blind date with my girlfriend’s friend?" },
        { week: 15, source: "Day075 교재1", ko: "진짜 적금 계좌 안 만드실 거예요? 시중 은행 중에 저희 금리가 제일 세거든요.", en: "Are you sure you don’t want to open a savings account? We’re offering higher interest rates than anyone else." },
        { week: 15, source: "Day075 교재2", ko: "진짜 우리랑 다른 바에 안 갈 거야?", en: "Are you sure you don’t want to come with us to another bar?" },
        { week: 15, source: "Day075 교재2", ko: "응. 내일 아침 9시에 발표가 있어서, 잠을 좀 자 둬야 해.", en: "Yeah. I have to give a presentation tomorrow at 9 a.m., so I should really get some sleep." },
        { week: 15, source: "Day075 교재2", ko: "진짜 이 회 안 먹을 거야?", en: "Are you sure you don’t wanna try this raw fish?" },
        { week: 15, source: "Day075 교재2", ko: "마지막으로 말하는데, 안 먹는다고. 차라리 굶었으면 굶었지 안 익힌 건 안 먹어.", en: "For the last time, yes. I’d rather go hungry than eat anything raw." },
        { week: 15, source: "Day075 교재2", ko: "여기요. 다 입어 봤는데, 저한테는 잘 안 어울리는 것 같네요.", en: "Here, I’m done trying this on, and I don’t think it’s really for me." },
        { week: 15, source: "Day075 교재2", ko: "알겠습니다. 그런데 진짜 안 사시게요? 이번 주만 50% 할인해 드리는데요.", en: "Okay, but are you sure you’re not gonna buy it? It’s 50% off only this week." },
        { week: 15, source: "Day075 교재3", ko: "Jason 씨, 지난 한 해 노고에 진심으로 감사드립니다. 당신이 아니었으면 프로젝트가 성공하지 못했을 거예요. 그런데 저희 팀과 다음 프로젝트를 진짜로 같이 안 하실 건가요? 프로젝트 멤버 전원에게 한 달 치 급여와 맞먹는 두둑한 보너스를 보장하겠습니다. 이런 기회를 놓치고 싶지 않으실 것 같은데요.", en: "I am so thankful for your hard work over the past year, Jason. I don’t think the project would have been successful without you. Now, are you sure you don’t want to stay with the team for our upcoming project? I can guarantee that all members will get a fat bonus equal to at least one month’s salary. You don’t want to miss out on this career opportunity." },
        { week: 15, source: "Day075 교재4", ko: "마트 영업 끝나기 직전에 가면, 조리 식품을 30% 할인된 가격에 살 수 있어.", en: "If you go to the store just before closing, you can get like 30% off on prepared food." },
        { week: 15, source: "Day075 교재4", ko: "새 모델이 다음 주에 할인에 들어갑니다.", en: "The new model goes on sale next week." },
        { week: 15, source: "Day075 교재4", ko: "원래는 이 초밥 살 생각이 없었는데, 보니까 60% 세일을 하더라고.", en: "I didn’t plan on buying this sushi, but I saw it was marked down 60%." },
        { week: 15, source: "Day075 대표", ko: "정말로 내 초밥 안 먹어 볼 거야? 진짜 맛있는데.", en: "Are you sure you don’t want to try my sushi? It’s really good." },

        // Week 16
        { week: 16, source: "Day076 교재1", ko: "(지갑을 잃어 돈을 빌렸을 때) 어젯밤 일은 미안해. 내가 지갑 찾으면 바로 갚을게.", en: "Sorry about last night. I’ll definitely pay you back, as soon as I find my wallet." },
        { week: 16, source: "Day076 교재1", ko: "(접촉 사고를 낸 운전자가) 어제 일은 미안합니다. 걱정 마세요. 제 보험회사에서 모든 비용을 지불해 줄 겁니다.", en: "Sorry about yesterday. Please don’t worry. I’m sure my insurance will cover everything." },
        { week: 16, source: "Day076 교재1", ko: "(실수로 상대방에게 커피를 쏟았을 때) 오늘 아침 일은 미안해. 앞으로는 (커피) 좀 조심해야겠어.", en: "Sorry about this morning. I should be more careful with my coffee." },
        { week: 16, source: "Day076 교재1", ko: "(약속을 못 지켰을 때) 오늘 아침엔 죄송했어요. 알람 맞춰 놓는 걸 깜박했어요.", en: "Sorry about this morning. I forgot to set my alarm." },
        { week: 16, source: "Day076 교재1", ko: "(아내 생일을 깜박한 남편이) 어제는 미안했어. 이번 주말에 뭐 사러 가자.", en: "Sorry about yesterday. I’ll take you shopping this weekend." },
        { week: 16, source: "Day076 교재2", ko: "어젯밤엔 미안했어요. 제가 종업원한테 그렇게 행동하지 말았어야 했는데.", en: "Sorry about last night. I shouldn’t have acted like that with the waiter." },
        { week: 16, source: "Day076 교재2", ko: "괜찮아요. 당신 잘못도 아닌데요.", en: "It’s okay. I don’t think it was really your fault." },
        { week: 16, source: "Day076 교재2", ko: "아까는 미안했어. 사장님이 들어오셨는데, 근무 중에는 전화하면 안 되거든.", en: "Sorry about earlier. My boss came in, and I’m not supposed to be on the phone during work." },
        { week: 16, source: "Day076 교재2", ko: "나 아직 맘 상했다고! 그렇다고 전화를 그렇게 끊을 건 없잖아.", en: "I’m still hurt. You don’t have to cut me off like that." },
        { week: 16, source: "Day076 교재2", ko: "여기서 보게 되다니 다행이군요. 오늘 아침 일은 미안했어요.", en: "I’m glad I ran into you here. Sorry about this morning." },
        { week: 16, source: "Day076 교재2", ko: "괜찮아요. 마감 시간 맞추느라 스트레스 많으신 거 알아요.", en: "It’s okay. I know you’ve been under a lot of pressure to meet our deadline." },
        { week: 16, source: "Day076 교재3", ko: "안녕하세요, Melinda. 오늘 아침에는 미안했어요. 언니 전화라 받아야 해서 회의 중에 나갔습니다. 저희 삼촌이 병원에 입원 중인데, 삼촌 상태에 대해 저한테 알려 줄 게 있나 했거든요. 알고 보니 중요한 내용은 아니었습니다.", en: "Hi, Melinda. Sorry about this morning. I left in the middle of the meeting because I had to take a call from my sister. My uncle is in the hospital, and I thought she had an update on how he was doing. It turned out it was nothing serious, though." },
        { week: 16, source: "Day076 교재4", ko: "왜 이렇게 늦었어?", en: "What kept you so long?" },
        { week: 16, source: "Day076 교재4", ko: "길이 너무 막혔어.", en: "Traffic was terrible." },
        { week: 16, source: "Day076 교재4", ko: "길이 너무 막혔어.", en: "Traffic was so bad." },
        { week: 16, source: "Day076 교재4", ko: "서울은 물가가 비싸.", en: "Seoul is expensive." },
        { week: 16, source: "Day076 교재4", ko: "백화점 물건은 너무 비싸.", en: "Department stores are super expensive." },
        { week: 16, source: "Day076 대표", ko: "아까는 미안. 휴대폰 배터리가 나가서.", en: "Sorry about earlier. My phone died." },
        { week: 16, source: "Day077 교재1", ko: "아직 좀 더 가야 해. 10분 늦어.", en: "I am not there yet. I am running 10 minutes late." },
        { week: 16, source: "Day077 교재1", ko: "휴게소에 화장실이 있을 거야. 근데 아직 더 가야 해.", en: "The rest area will have a bathroom, but we’re not quite there yet." },
        { week: 16, source: "Day077 교재1", ko: "마스크 의무화를 해제하려면 일일 확진자 수가 오천 명 아래로 떨어져야 합니다. 아직은 그 정도가 아닙니다.", en: "Before lifting the mask mandate, cases should be at less than 5,000 a day. We are not there yet." },
        { week: 16, source: "Day077 교재1", ko: "그 여자 좋긴 한데, 아직 결혼할 정돈 아니야. 한 1년쯤 후에나 결혼할 듯.", en: "I like her, but we’re not there yet. Maybe we can get married in a year or so." },
        { week: 16, source: "Day077 교재1", ko: "기술이 많이 발전하긴 했지만, 아직은 부족합니다.", en: "The technology is advanced enough, but we are not there yet." },
        { week: 16, source: "Day077 교재2", ko: "죄송한데요. 배가 조금 고프네요. 저녁 시간인가요?", en: "Excuse me. I’m getting a bit hungry. Is it time for dinner?" },
        { week: 16, source: "Day077 교재2", ko: "죄송합니다. 도착하기까지 2시간 남았을 때 석식 서비스가 시작될 예정이라 아직 좀 남았습니다.", en: "I’m sorry. We plan on starting the dinner service when we are two hours from our destination, and we’re not there yet." },
        { week: 16, source: "Day077 교재2", ko: "금리를 올릴 시점이라고 생각하시는지요?", en: "Do you think it’s time to raise interest rates?" },
        { week: 16, source: "Day077 교재2", ko: "소비자 물가 지수를 보면 아직 그 정도는 아닙니다. 다음 회의 때까지 인플레이션이 7%까지 올라가면, 고려해 볼 생각입니다.", en: "According to the consumer price index, we’re not there yet. If inflation reaches 7% by our next meeting, we will consider it." },
        { week: 16, source: "Day077 교재3", ko: "저희 도요타는 소비자들이 최신 기술을 요구한다는 점, 그리고 자율 주행차 개발을 손꼽아 기다리고 있다는 점을 잘 알고 있습니다. 하지만 아직은 도요타 최초의 자율 주행차 판매 시점을 말씀드릴 수가 없으며, 아직 기술적으로 완성되지 않았기 때문입니다. 우리는 고객의 안전을 위해 최선을 다하고 있으며 테스트를 계속할 것입니다.", en: "At Toyota, we are aware that consumers demand the latest technologies, and they are looking forward to the development of self-driving vehicles. Unfortunately, we are unable to announce when sales of our first such cars can begin, because the technology is simply not there yet. We remain committed to the safety of our customers and will continue testing." },
        { week: 16, source: "Day077 교재4", ko: "서울의 대중교통은 매우 훌륭하다.", en: "Seoul’s public transportation is great." },
        { week: 16, source: "Day077 교재4", ko: "한국 경제가 좋지 않은 상황이다.", en: "The Korean economy is in bad shape." },
        { week: 16, source: "Day077 대표", ko: "도착하려면 아직 좀 남았어요.", en: "We are not there yet." },
        { week: 16, source: "Day078 교재1", ko: "내가 지갑을 안 가지고 온 듯. 계산 좀 부탁해도 될까?", en: "I think I forgot my wallet. Could you take care of this?" },
        { week: 16, source: "Day078 교재1", ko: "집에 열쇠를 두고 왔어.", en: "I forgot my keys at home." },
        { week: 16, source: "Day078 교재1", ko: "휴대폰을 안 가지고 왔네. 다시 가서 가져올 시간 될까?", en: "I forgot my phone. Do you think I have enough time to go back and get it?" },
        { week: 16, source: "Day078 교재1", ko: "(영화 <나 홀로 집에서> 중에서) Kevin을 집에 두고 왔어요!", en: "We forgot Kevin!" },
        { week: 16, source: "Day078 교재1", ko: "저는 점심 먹고 약 먹는 걸 항상 깜박해요.", en: "I always forget to take my pills after lunch." },
        { week: 16, source: "Day078 교재2", ko: "다음에 오는 택시를 잡아 볼게요.", en: "I’ll try and grab the next taxi that comes by." },
        { week: 16, source: "Day078 교재2", ko: "잠시만요! Tom 생일 선물 사는 걸 깜박했어요. 다시 가게에 들어가서 선물부터 사 올게요.", en: "Oh, wait! I forgot Tom’s birthday present. I’ll go back in and grab it first." },
        { week: 16, source: "Day078 교재2", ko: "시작합시다. 과제 꺼내서 채점을 위해 저에게 주세요.", en: "Let’s begin. Please take out your homework and hand it to me for grading." },
        { week: 16, source: "Day078 교재2", ko: "음, Moore 선생님? 죄송한데 과제를 안 가져왔어요.", en: "Umm, Ms. Moore? I’m afraid I forgot my homework" },
        { week: 16, source: "Day078 교재2", ko: "죄송한데, 제가 구인 공고 올리는 걸 깜박했네요.", en: "I’m sorry, Sir, but I realize I forgot to put up your job opening." },
        { week: 16, source: "Day078 교재2", ko: "괜찮아요. 언제쯤 올라간다고 보면 될까요?", en: "That’s fine. When can I expect it to be posted?" },
        { week: 16, source: "Day078 교재3", ko: "목 토시 챙겨 오세요! 시내는 이제 날씨가 그렇게 춥지 않지만, 산에서는 훨씬 더 추울 겁니다. 게다가, 일기 예보에 따르면 기온이 영하 10도까지 내려갈 수도 있다고 합니다. 눈이 올 때를 대비해 등산용 아이젠을 챙겨 오셔도 됩니다.", en: "Please don’t forget your neck gaiters. The weather isn’t that bad now in the city, but it will be much colder on the mountain. Besides, the weather forecast says the temperatures might get down to minus 10 degrees. You might even want to bring crampons, just in case it snows." },
        { week: 16, source: "Day078 교재4", ko: "여자들한테 잘 보이려고 불어를 좀 배워 봤는데, 잘 안되더군요.", en: "I tried learning French to impress women, but that didn’t work." },
        { week: 16, source: "Day078 교재4", ko: "제가 불어를 나름 열심히 배워 봤는데, 발음조차 제대로 할 수 없더라고요.", en: "I tried to learn French, but I couldn’t even get the pronunciation right." },
        { week: 16, source: "Day078 교재4", ko: "연료가 간당간당한데, 그래도 뭐 부산까지 한번 달려 보지 뭐.", en: "I am low on gas, but I’m going to just try and make it all the way to Busan." },
        { week: 16, source: "Day078 대표", ko: "휴대폰 충전기를 회사에 놔두고 왔네.", en: "I forgot my phone charger at work." },
        { week: 16, source: "Day079 교재1", ko: "너무 춥다. 이런 날씨는 또 처음이군.", en: "It’s super cold. I have never seen any weather like this." },
        { week: 16, source: "Day079 교재1", ko: "이른 오후 시간에는 보통 (교통) 상황이 이렇지는 않은데.", en: "Things aren’t normally like this so early in the afternoon." },
        { week: 16, source: "Day079 교재1", ko: "이 정도로 유려한 디자인은 본 적이 없습니다. 공상 과학 영화에서 바로 나온 것 같은 차네요.", en: "I’ve never seen a sleek design like this. This car looks like it came straight out of a sci-fi movie." },
        { week: 16, source: "Day079 교재1", ko: "상황이 이런 적은 처음입니다.", en: "Things have never been like this." },
        { week: 16, source: "Day079 교재1", ko: "이렇게 맛있는 디저트는 처음이야. 이게 이름이 뭐라고?", en: "I’ve never tasted any dessert like this. What did you call it?" },
        { week: 16, source: "Day079 교재2", ko: "무슨 일이 있었는지 알아? 하룻밤 사이 구독자가 천 명이나 늘었어. 이런 적은 처음이거든.", en: "Do you know what happened? I got a thousand subscribers overnight. Things have never been like this." },
        { week: 16, source: "Day079 교재2", ko: "어젯밤에 어떤 코미디언이 TV에서 네 유튜브 채널에 대해 언급한 거 같은데.", en: "I think a comedian mentioned your channel on TV last night." },
        { week: 16, source: "Day079 교재2", ko: "시청에 무슨 일이지? 사람이 저렇게 많이 모인 건 처음 보네.", en: "What’s going on at City Hall? I’ve never seen a crowd like this." },
        { week: 16, source: "Day079 교재2", ko: "시장 스캔들 기억하지? 그녀의 사임을 촉구하고 있는 것 같아.", en: "Do you remember the mayor’s scandal? I think they’re trying to force her to step down." },
        { week: 16, source: "Day079 교재2", ko: "주택 가격이 급락하고 있는 점에 대해 어떻게 생각하나요?", en: "What do you think about the drop in housing prices?" },
        { week: 16, source: "Day079 교재2", ko: "제가 부동산 중개업을 20년 넘게 하고 있는데, 이런 일은 처음입니다.", en: "I’ve been working as a realtor for over 20 years, and I’ve never seen anything like this." },
        { week: 16, source: "Day079 교재3", ko: "수요가 너무 많아서, 오늘은 정상 영업시간보다 4시간 일찍 문을 닫아야 할 것 같습니다. 사과 말씀드립니다. 저희 가게 젤라토가 부드럽고 맛있기는 하지만, 이 정도로 찾는 사람이 많은 건 처음입니다. 다음 주에는 물량을 늘리기 위해 노력하겠습니다.", en: "Due to overwhelming demand, we’re afraid that we have to close four hours before our normal closing time today. Our apologies. Even though we know our gelato is creamy and delicious, we’ve never seen demand like this. We will work on increasing our capacity for next week." },
        { week: 16, source: "Day079 교재4", ko: "수진이가 다음 달에 결혼한다고 내가 말했던가?", en: "Did I mention that Sujin is getting married next month?" },
        { week: 16, source: "Day079 교재4", ko: "내가 이사한다고 얘기했던가?", en: "Did I mention that I am moving?" },
        { week: 16, source: "Day079 교재4", ko: "지난번에 오늘 저녁 식사 같이 못 한다고 말한다는 걸 깜박했어.", en: "I forgot to mention last time that I won’t be able to join you for dinner tonight." },
        { week: 16, source: "Day079 교재4", ko: "메뉴에 세금이 포함되어 있지 않다고 나와 있지 않네요.", en: "The menu doesn’t mention the tax isn’t included." },
        { week: 16, source: "Day079 대표", ko: "이런 경우는 또 처음 보네요.", en: "I have never seen anything like this." },
        { week: 16, source: "Day080 교재1", ko: "나 지금 스타벅스에서 커피 사고 있어.", en: "I am at Starbucks, grabbing some coffee." },
        { week: 16, source: "Day080 교재1", ko: "제 상사께서 공항에 부사장님 마중 나가고 안 계십니다.", en: "My boss is out, picking up the VP from the airport." },
        { week: 16, source: "Day080 교재1", ko: "네가 전화했을 때, 거실에서 <에밀리 파리에 가다>를 보고 있었어.", en: "I was in the living room, watching Emily in Paris when you called" },
        { week: 16, source: "Day080 교재1", ko: "저희가 술집에서 위스키를 마시고 있는데 싸움이 벌어졌어요.", en: "We were at the bar, drinking some whisky when a fight broke out." },
        { week: 16, source: "Day080 교재1", ko: "저는 청담에 있는 BMW 전시장에서 SUV 신차를 보고 있었습니다.", en: "I was at the BMW dealership in Cheongdam, checking out the new SUV." },
        { week: 16, source: "Day080 교재2", ko: "거의 다 왔나요? 5분 후에 회식 시작해요.", en: "Are you almost here? Dinner starts in 5 minutes." },
        { week: 16, source: "Day080 교재2", ko: "저 사실 올리브영에서 핸드크림 보고 있어요. 10분 후에 도착할 것 같습니다.", en: "I’m actually at Olive Young, looking for hand cream. I should be there in 10 minutes." },
        { week: 16, source: "Day080 교재2", ko: "미안, 나 조금 늦어. 벌써 영화관에 도착한 거야?", en: "Sorry, I’m running a little late. Are you already at the movie theater?" },
        { week: 16, source: "Day080 교재2", ko: "건너편 카페에서 너 기다리고 있어.", en: "I’m at the cafe across the street, waiting for you." },
        { week: 16, source: "Day080 교재2", ko: "아까 전화했는데 어디 있었어?", en: "Where were you when I tried calling you earlier?" },
        { week: 16, source: "Day080 교재2", ko: "팀장한테 엄청 깨지면서 회의실에 있었지.", en: "I was in the conference room, getting chewed out by my manager." },
        { week: 16, source: "Day080 교재3", ko: "저희가 마포에 있는 빵집에서 빵을 사고 있는데 제가 가장 좋아하는 배우 중 한 명을 봤어요. TV에서보다 실물이 훨씬 잘생겼더군요. 다가가서 사인을 부탁했는데, 바쁘다며 거절을 하는 거예요! 그래서 그가 나오는 건 뭐든 안 봅니다.", en: "We were at a bakery in Mapo, picking up some bread when we ran into one of my favorite actors. He looked much better in person than he does on TV. But when I walked up to him and asked him for an autograph, he turned me down, saying he was in a rush! That’s why I refuse to watch anything with him in it." },
        { week: 16, source: "Day080 교재4", ko: "입구 쪽에서 보자.", en: "I will see you at the entrance." },
        { week: 16, source: "Day080 교재4", ko: "H 마트는 코리아타운 입구 쪽에 위치한다.", en: "H Mart is located at the entrance of Koreatown." },
        { week: 16, source: "Day080 교재4", ko: "역삼역 3번 출구에서 보는 게 어때?", en: "How about we meet at Yeoksam Station, exit 3?" },
        { week: 16, source: "Day080 교재4", ko: "네가 하루 종일 책상에 앉아서 일을 하니까 허리가 아픈 걸 거야.", en: "Your back is probably sore from sitting at a desk all day." },
        { week: 16, source: "Day080 대표", ko: "나 저녁 사가려고 한솥도시락에 있어.", en: "I am at Hansot, picking up dinner." },

        // Week 17
        { week: 17, source: "Day081 교재1", ko: "선생님 생일 선물로 이 비타민을 해 드리면 어떨까 하는데.", en: "I thought maybe we could get our teacher these vitamins for her birthday." },
        { week: 17, source: "Day081 교재1", ko: "직접 만나지 말고 줌으로 회의하면 어떨까 싶습니다.", en: "I thought maybe we could have a Zoom meeting instead of one in person." },
        { week: 17, source: "Day081 교재1", ko: "이번 여행 때 기차표를 대량 구매하지 말고 버스 전세를 내면 어떨까 하는데요.", en: "I thought maybe we could rent a bus for our trip, instead of buying a bunch of train tickets." },
        { week: 17, source: "Day081 교재1", ko: "혹시 당신이 주요 고객사에 신입 사원을 소개해 주면 어떨까요?", en: "I thought maybe you could introduce the new hire to our major clients." },
        { week: 17, source: "Day081 교재1", ko: "다음 한 주는 온전히 쉬고, 새해 지나서 상쾌하게 다시 보는 게 어떨까요?", en: "I thought maybe we could take the whole week off next week, so we could come back refreshed after New Year’s." },
        { week: 17, source: "Day081 교재2", ko: "너 그렇게 안 바쁘면, 언제 술 한잔하면 어떨까 하는데.", en: "If you’re not too busy, I thought maybe we could get a drink sometime." },
        { week: 17, source: "Day081 교재2", ko: "좋지. 안 그래도 나도 그 생각 했는데.", en: "Sure. I was thinking the same thing." },
        { week: 17, source: "Day081 교재2", ko: "제가 출장 와 있는 동안 한번 뵐까요?", en: "Do you want to get together while I’m on my business trip?" },
        { week: 17, source: "Day081 교재2", ko: "네, 여기 계시는 마지막 날 같이 나가서 저녁 하면 어떨까 합니다.", en: "Yeah, I thought maybe we could go out and get dinner on the last day you’re here." },
        { week: 17, source: "Day081 교재2", ko: "선생님, 제 학생 중 한 명이 자기소개서를 첨삭해 줄 분을 구하고 있어요. 생각 있으실지 해서요.", en: "Sir, one of my students is looking for someone to help her edit her cover letter. I thought maybe you’d be interested." },
        { week: 17, source: "Day081 교재2", ko: "당연하죠. 이번 주에 좀 한가합니다. 그분한테 제 연락처 주셔도 됩니다.", en: "Sure. I have some free time this week. Please feel free to give her my contact info." },
        { week: 17, source: "Day081 교재3", ko: "안녕, 얘들아. 일기 예보를 보다가 이번 주말에 등산 가면 어떨까 싶더라고. 나 캠핑용 난로 등등 다 있어서, 너희들은 아무 장비도 안 가져와도 돼. 편하게 알려줘. 단풍이 금방 질 거야.", en: "Hey guys. I was looking at the weather forecast and thought maybe we could go hiking this weekend. I have a camping stove and everything, so you wouldn’t need to bring any equipment. Just let me know. The fall colors aren’t going to last much longer." },
        { week: 17, source: "Day081 교재4", ko: "혹시 이 신발 다른 사이즈도 있을까요?", en: "I was wondering if you have these shoes in another size." },
        { week: 17, source: "Day081 교재4", ko: "혹시 추천서 좀 써 주실 수 있을까요?", en: "I was hoping that you could write a letter of recommendation for me." },
        { week: 17, source: "Day081 교재4", ko: "우리 수업을 8월에 시작했으면 어떨까 하는데, 그때 괜찮으신가요?", en: "I was hoping to start our sessions in August. Would that work for you?" },
        { week: 17, source: "Day081 교재4", ko: "영업시간 이후라는 건 아는데, 혹시 8시 15분에 매장에 잠깐 들러도 괜찮을까요?", en: "I know it’s just after your hours, but would it be alright if I swung by the store at 8:15?" },
        { week: 17, source: "Day081 대표", ko: "그냥 식당 예약한 것 취소하고 집에 있으면 어떨까 하는데.", en: "I thought maybe we could cancel the reservation and just stay at home." },
        { week: 17, source: "Day082 교재1", ko: "저희가 인테리어를 다 바꾸었는데도, 분위기가 그대로네요.", en: "We remodeled the whole interior, but that still didn’t change the atmosphere." },
        { week: 17, source: "Day082 교재1", ko: "셔츠를 안에 넣어 입으면 내가 좀 날씬해 보이니?", en: "Does it make me look skinnier when I tuck in my shirt?" },
        { week: 17, source: "Day082 교재1", ko: "당신이 나한테 거짓말하면 나 너무 속상해.", en: "It really hurts my feelings when you lie to me." },
        { week: 17, source: "Day082 교재1", ko: "줌 회의에서는 누군가 말을 하면 그 사람이 큰 화면에 뜹니다.", en: "When someone is speaking in a Zoom meeting, it puts them on the big screen." },
        { week: 17, source: "Day082 교재2", ko: "런던에서 14시간 비행기를 타고 방금 도착하셨어요. 내일 경기 괜찮겠어요?", en: "You just got off a 14-hour flight from London. Will you be okay for the match tomorrow?" },
        { week: 17, source: "Day082 교재2", ko: "장거리 비행에 꽤 익숙한 편이지만, 어느 정도는 제 경기력에 영향을 미칠 수 있긴 합니다.", en: "I’m quite used to long-haul flights, but I admit that can hurt my performance to some degree." },
        { week: 17, source: "Day082 교재2", ko: "정부가 또 금리를 올렸나 봐.", en: "It seems like the government has raised interest rates again." },
        { week: 17, source: "Day082 교재2", ko: "그랬지. 근데 그래도 인플레이션을 완화하는 데 별 도움이 안 되는 듯해.", en: "They have. But it hasn’t actually helped to curb inflation." },
        { week: 17, source: "Day082 교재2", ko: "더러운 접시를 그냥 두고 나보고 설거지하라는 식으로 그러면 나 정말 화나거든.", en: "It really pisses me off when you leave dirty dishes and expect me to do them." },
        { week: 17, source: "Day082 교재2", ko: "난 당신이 설거지 좋아하는 줄 알았지.", en: "I thought you enjoyed doing dishes." },
        { week: 17, source: "Day082 교재3", ko: "다른 팀에서 모닝 메뉴를 없앨 계획을 하고 있다고 들었습니다. 저희는 반대하는데 그렇게 되면 충성도 높은 고객들이 등을 돌릴 수 있기 때문입니다. 저희 조사에 따르면, 조사 대상 고객의 20%가 일주일에 최소 한 번은 아침을 먹기 위해 방문합니다. 경쟁사에 고객을 빼앗길 수 있는 위험을 감수하고 싶지 않습니다.", en: "We heard that another team has a plan to get rid of our morning menu. We want to speak out against the idea, because that would definitely push away some of our loyal customers. According to our research, 20% of surveyed customers come in at least once a week to eat breakfast. We don’t want to risk losing them to competitors." },
        { week: 17, source: "Day082 교재4", ko: "Harry Kane 선수가 전반 5분 만에 득점함으로써 팀이 일찌감치 앞서 나가게 되었습니다.", en: "Harry Kane scored 5 minutes into the first half and that put them ahead early on." },
        { week: 17, source: "Day082 교재4", ko: "제가 내리기 전에 사람들이 엘리베이터에 타면 정말 짜증이 나요.", en: "It really bothers me when people get in the elevator before I can get off." },
        { week: 17, source: "Day082 교재4", ko: "늦게 일어나면 하루가 엉망이 됩니다.", en: "It ruins my day when I wake up late." },
        { week: 17, source: "Day082 대표", ko: "진통제를 먹었는데도 두통이 가시질 않아.", en: "I took a painkiller, but that didn’t relieve my migraine." },
        { week: 17, source: "Day083 교재1", ko: "저희 겨울 컬렉션 제품 보고 싶어 하실 듯해서요.", en: "I thought you would be interested in taking a peek at our winter collection." },
        { week: 17, source: "Day083 교재1", ko: "저희 수업에 관심 있으시면, englishnow.com을 방문해 주세요.", en: "If you’re interested in our classes, please visit www.englishnow.com." },
        { week: 17, source: "Day083 교재1", ko: "저 신용카드 하나 더 안 만들어도 되거든요.", en: "I’m not really interested in getting another credit card." },
        { week: 17, source: "Day083 교재1", ko: "너 항상 AI 이야기 하던데, 이 기사 관심 있을 것 같아서.", en: "Since you’re always talking about AI, I thought you would be interested in this article." },
        { week: 17, source: "Day083 교재1", ko: "공석에 관심 있으시면, 언제든 제게 연락 주세요.", en: "If you’re interested in the opening, feel free to contact me at any time." },
        { week: 17, source: "Day083 교재2", ko: "제 남편이 새 차를 사고 싶어 하는 눈치예요. 왜 차에 환장을 하는지 이해가 안 가요. 이미 스포츠카 두 대가 있거든요.", en: "My husband seems interested in buying a new car. I don’t really get why he is so crazy about them. He has two sports cars already." },
        { week: 17, source: "Day083 교재2", ko: "근데 부러워요. 적어도 남편분은 능력이라도 되니.", en: "I am envious of you, though. At least your husband can afford them." },
        { week: 17, source: "Day083 교재2", ko: "혹시 Hailey한테 관심 있을까? 너희 둘 자리 마련해 줄까?", en: "Would you be interested in Hailey? Can I set you two up?" },
        { week: 17, source: "Day083 교재2", ko: "내가 Samantha랑 만난다고 하지 않았었나?", en: "Didn’t I mention that I’m going out with Samantha?" },
        { week: 17, source: "Day083 교재2", ko: "다른 프로젝트 하나 더 맡을 생각 있나요, 민수 씨?", en: "Are you interested in taking on another project, Minsu?" },
        { week: 17, source: "Day083 교재2", ko: "죄송한데 이미 일이 너무 많아서요.", en: "I’m afraid I already have too much on my plate." },
        { week: 17, source: "Day083 교재3", ko: "인사과에서 리우데자네이루 지사의 기업 교육 담당자 자리에 지원할 사람을 구하고 있습니다. 2년간 해외 근무에 관심이 있는 분은 hr@abccorporation.com으로 이력서와 자기소개서를 송부해 주시기를 바랍니다. 이 직책에는 무료 주택, 회사 차량, 포르투갈어 수업과 같은 모든 종류의 특전이 제공됩니다.", en: "HR is looking for someone to fill a corporate trainer position at the Rio de Janeiro branch office. If you’re interested in working and living abroad for two years, please send your résumé and a cover letter to hr@abccorporation.com. The position comes with all kinds of perks, like free housing, a company car, and Portuguese lessons." },
        { week: 17, source: "Day083 교재4", ko: "네가 나에게 상대가 된다고 생각해?", en: "You think you could take me on?" },
        { week: 17, source: "Day083 교재4", ko: "네가 원하지 않는다면 내가 그 프로젝트 맡을게.", en: "I will take on the project if you don’t want to." },
        { week: 17, source: "Day083 교재4", ko: "상점들은 주로 크리스마스 시즌 동안 추가 직원을 채용한다.", en: "Shops often take on extra employees during the Christmas season." },
        { week: 17, source: "Day083 교재4", ko: "그 여자는 남자 친구랑 같이 있으면 성격이 바뀐다.", en: "She takes on a different personality when she is with her boyfriend." },
        { week: 17, source: "Day083 대표", ko: "추가로 보험 하나 더 가입할 생각은 없습니다.", en: "I am not really interested in buying another insurance plan." },
        { week: 17, source: "Day084 교재1", ko: "잠깐 시간 되세요? 곧 있을 워크숍 관련해서 이야기 좀 하려고요.", en: "Have you got a minute? I need to talk to you about the upcoming workshop." },
        { week: 17, source: "Day084 교재1", ko: "잠깐 시간 되세요? 제 자기소개서 관련해서 간단한 질문이 하나 있어서요.", en: "Have you got a minute? I have a quick question about my cover letter." },
        { week: 17, source: "Day084 교재1", ko: "잠깐 시간 되세요? 히터가 고장이 났는데 고치는 방법을 모르겠어요.", en: "Do you have a minute? My heater isn’t working and I don’t know how to fix it." },
        { week: 17, source: "Day084 교재1", ko: "잠깐 시간 돼? 네가 말한 파일을 못 찾겠어.", en: "Do you have a minute? I can’t find the file you mentioned." },
        { week: 17, source: "Day084 교재2", ko: "안녕, Sally! 잠깐 시간 돼? 그나저나 너 오늘 좀 힘이 없어 보인다.", en: "Hi, Sally! Have you got a minute? By the way, you look a little low on energy today." },
        { week: 17, source: "Day084 교재2", ko: "응, 어젯밤에 파티하느라 늦게까지 놀았거든. 근데 무슨 일?", en: "Yeah, I stayed up late partying last night. What’s up?" },
        { week: 17, source: "Day084 교재2", ko: "여보, 잠깐 시간 돼? 나 선반 꼭대기에 있는 와인 잔에 손이 안 닿아.", en: "Honey, have you got a second? I can’t reach the wine glasses on the top shelf." },
        { week: 17, source: "Day084 교재2", ko: "그래. 여기 있어. 나처럼 키 큰 남자랑 결혼해서 좋지, 응?", en: "Sure. Here you go. It’s a good thing you married such a tall guy, huh?" },
        { week: 17, source: "Day084 교재2", ko: "잠깐 시간 되나요? 점심시간 마치고 제 사무실에서 볼까요?", en: "Have you got a moment? Can we meet in my office after lunch?" },
        { week: 17, source: "Day084 교재2", ko: "혹시 어떤 일 때문에 그러시는지 여쭤봐도 될까요? 안 좋은 소식이면, 지금 당장 알고 싶어서요.", en: "May I ask what this is about? If it’s bad news, I’d like to know right away." },
        { week: 17, source: "Day084 교재3", ko: "저희가 문제를 해결해 드릴 수 있어서 다행입니다. 혹시 잠깐 시간 되시면, 통화 후에 전화 끊지 마세요. 오늘 고객 서비스 관련해서 몇 가지 질문에 답을 해 주시면 감사하겠습니다.", en: "I’m glad we were able to solve your problem. If you have a minute, please stay on the line after the call. I’d appreciate you answering some questions about your customer service experience today." },
        { week: 17, source: "Day084 교재4", ko: "잠깐 시간 좀 할애해 줄 수 있을까요?", en: "Do you have a minute to spare?" },
        { week: 17, source: "Day084 교재4", ko: "5분밖에 시간이 안 되네요. 빨리 말씀해 주실 수 있을까요?", en: "I’ve got only five minutes to spare. Can you make it quick?" },
        { week: 17, source: "Day084 교재4", ko: "딱 5분이면 됩니다.", en: "I just need five minutes of your time." },
        { week: 17, source: "Day084 교재4", ko: "잠깐이면 됩니다.", en: "This will only take a minute." },
        { week: 17, source: "Day084 교재4", ko: "시간을 너무 많이 뺏어서 죄송합니다.", en: "Sorry for taking up so much of your time." },
        { week: 17, source: "Day084 대표", ko: "너 잠깐 시간 되니? 내가 작업 중인 로고를 보여주고 싶어서.", en: "Hey, have you got a minute? I’d like to show you the logo I’ve been working on." },
        { week: 17, source: "Day085 교재1", ko: "너 이 동네 잘 아는 듯하네.", en: "You seem quite familiar with this neighborhood." },
        { week: 17, source: "Day085 교재1", ko: "저는 수년 동안 준비반을 가르쳤기 때문에 오픽에 대해 아주 잘 알고 있습니다.", en: "I am quite familiar with OPIc, having taught preparatory classes for years." },
        { week: 17, source: "Day085 교재1", ko: "그 술집이 밖에서 볼 때는 낯익지 않았는데, 안에 들어가 보니 예전에 한 번 왔었다 싶더군요.", en: "The bar didn’t look familiar from the outside, but when I went in, I realized I had been there before." },
        { week: 17, source: "Day085 교재1", ko: "남산 북쪽으로는 등산을 안 해 봤다고 생각했는데, 막상 와 보니 전에 와 본 걸 알겠네요.", en: "I didn’t think I’d hiked the north side of Namsan before, but now that I’m here, it seems familiar." },
        { week: 17, source: "Day085 교재2", ko: "어디서 뵙지 않았나요? 매우 낯이 익은데요.", en: "Do I know you from somewhere? You look very familiar." },
        { week: 17, source: "Day085 교재2", ko: "아닌데요. 뵌 적 없는 듯합니다.", en: "No, I don’t think we’ve ever met." },
        { week: 17, source: "Day085 교재2", ko: "BNPL이라고 들어 보셨나요?", en: "Are you familiar with BNPL?" },
        { week: 17, source: "Day085 교재2", ko: "아니요. 못 들어 봤어요. 그나저나 BNPL이 무엇의 약자인가요?", en: "No, I’m not. What does BNPL stand for, by the way?" },
        { week: 17, source: "Day085 교재2", ko: "이 광고 음악 어디서 들어 본 듯. 뭔지 아니?", en: "The music in this commercial sounds familiar. Do you know what it is?" },
        { week: 17, source: "Day085 교재2", ko: "응, 신중현 씨가 만든 예전 노래잖아. 노래 제목이 뭐더라? 생각이 날 듯 말 듯 하네.", en: "Yeah, it’s an old song by Shin Joong-hyun. What’s the name? It’s on the tip of my tongue." },
        { week: 17, source: "Day085 교재3", ko: "‘파이어 운동’이라는 말을 들어 보지 못한 분들을 위해 말씀드리자면, ‘경제적 독립 조기 은퇴’의 줄임말입니다. 젊었을 때 저축해서 최대한 빨리 은퇴를 하는 것이 핵심이죠. 이런 분들은 일에서 의미를 찾기보다 시간과 에너지를 가족, 여행 등에 쓰는 걸 중요하게 생각합니다.", en: "For those who may not be familiar with the “FIRE movement”, it stands for “Financial Independence, Retire Early.” It’s all about saving money while you’re young, so you can make your career as short as possible. These people don’t find meaning in work and would rather spend their time and energy on other things, like family and travel." },
        { week: 17, source: "Day085 교재4", ko: "이 표현을 많이 본 것 같은데, 쓰기는 어렵네. 익숙해지려면 시간이 필요할 것 같아.", en: "I am quite familiar with this expression, but I still have trouble using it. I’m afraid it may take some time to get used to." },
        { week: 17, source: "Day085 교재4", ko: "A: 너 아직 해산물을 잘 못 먹는 듯하네.", en: "A: It seems like you are still not used to seafood." },
        { week: 17, source: "Day085 교재4", ko: "B: 아무리 노력해도 향이나 냄새가 적응이 안 되네.", en: "B: I can’t get used to the flavor and the smell." },
        { week: 17, source: "Day085 대표", ko: "명랑 핫도그라고 들어 봤니?", en: "Are you familiar with Myungrang Hotdogs?" }
    ];

    // 영어회화 난이도 분리
    const convEasy = rawConvData.filter(item => item.source.includes('대표') || item.source.includes('교재1'));
    const convHard = rawConvData.filter(item => !(item.source.includes('대표') || item.source.includes('교재1')));

    // 퀴즈 진행 상태 변수
    let currentQuestions = [];
    let currentIndex = 0;
    let isPhrasalMode = false;
    let starredQuestions = []; 

    function shuffleArray(array) {
        let shuffled = [...array];
        for (let i = shuffled.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
        }
        return shuffled;
    }

    // 선택된 주차에 맞게 필터링
    function filterByWeek(dataArray) {
        if (currentWeekFilter === 'all') {
            return dataArray.filter(item => item.week >= 13 && item.week <= 17);
        }
        return dataArray.filter(item => item.week === currentWeekFilter);
    }

    function startQuiz(mode) {
        let sourceArray = [];
        let titleMode = "";

        if (mode === 'phrasal-easy') { 
            sourceArray = phrasalEasy; isPhrasalMode = true; 
            titleMode = "🟢 구동사 순한맛 퀴즈"; 
        }
        else if (mode === 'phrasal-hard') { 
            sourceArray = phrasalHard; isPhrasalMode = true; 
            titleMode = "🔴 구동사 매운맛 퀴즈"; 
        }
        else if (mode === 'conv-easy') { 
            sourceArray = convEasy; isPhrasalMode = false; 
            titleMode = "💬 영어회화 순한맛 퀴즈"; 
        }
        else if (mode === 'conv-hard') { 
            sourceArray = convHard; isPhrasalMode = false; 
            titleMode = "🔥 영어회화 매운맛 퀴즈"; 
        }

        const filteredData = filterByWeek(sourceArray);

        if (filteredData.length === 0) {
            alert(`선택하신 주차(Week ${currentWeekFilter})에 해당하는 데이터가 아직 없습니다.`);
            return;
        }

        document.getElementById('mode-selection').classList.add('hidden');
        document.getElementById('quiz-area').classList.remove('hidden');
        
        let weekText = currentWeekFilter === 'all' ? " (Week 13~17 누적)" : ` (Week ${currentWeekFilter})`;
        document.getElementById('main-title').innerText = titleMode + weekText; 
        
        starredQuestions = []; 
        // 7문제만 추출 (데이터가 7개 미만이면 전체 추출)
        const qCount = Math.min(filteredData.length, 7);
        currentQuestions = shuffleArray(filteredData).slice(0, qCount);
        currentIndex = 0;
        
        loadQuestion();
    }

    function loadQuestion() {
        document.getElementById('answer-section').classList.add('hidden');
        document.getElementById('btn-next').classList.add('hidden');
        document.getElementById('btn-finish').classList.add('hidden');
        document.getElementById('meaning-info').classList.add('hidden');
        
        const koBox = document.getElementById('ko-box');
        koBox.style.cursor = 'pointer';
        koBox.style.pointerEvents = 'auto';

        const q = currentQuestions[currentIndex];
        document.getElementById('question-counter').innerText = `문제 ${currentIndex + 1} / ${currentQuestions.length}`;
        document.getElementById('ko-text').innerText = q.ko;
        document.getElementById('en-text').innerText = q.en;
        document.getElementById('source-info').innerText = `출처: ${q.source}`;
        
        if(isPhrasalMode && q.meaning) {
            document.getElementById('meaning-info').innerText = q.meaning;
        }

        const starBtn = document.getElementById('btn-star');
        if (starredQuestions.includes(q)) {
            starBtn.classList.add('active');
            starBtn.innerText = "⭐ 어려워요 (저장됨)";
        } else {
            starBtn.classList.remove('active');
            starBtn.innerText = "⭐ 어려워요";
        }
    }

    function showAnswer() {
        const koBox = document.getElementById('ko-box');
        koBox.style.cursor = 'default';
        koBox.style.pointerEvents = 'none';

        document.getElementById('answer-section').classList.remove('hidden');
        
        if(isPhrasalMode && currentQuestions[currentIndex].meaning) {
            document.getElementById('meaning-info').classList.remove('hidden');
        }
        
        if (currentIndex < currentQuestions.length - 1) {
            document.getElementById('btn-next').classList.remove('hidden');
        } else {
            document.getElementById('btn-finish').classList.remove('hidden');
        }
    }

    function toggleStar() {
        const q = currentQuestions[currentIndex];
        const starBtn = document.getElementById('btn-star');
        const index = starredQuestions.indexOf(q);
        
        if (index > -1) {
            starredQuestions.splice(index, 1);
            starBtn.classList.remove('active');
            starBtn.innerText = "⭐ 어려워요";
        } else {
            starredQuestions.push(q);
            starBtn.classList.add('active');
            starBtn.innerText = "⭐ 어려워요 (저장됨)";
        }
    }

    function playTTS() {
        const textToSpeak = currentQuestions[currentIndex].en;
        if ('speechSynthesis' in window) {
            window.speechSynthesis.cancel();
            const utterance = new SpeechSynthesisUtterance(textToSpeak);
            utterance.lang = 'en-US';
            utterance.rate = 0.9; 
            window.speechSynthesis.speak(utterance);
        } else {
            alert('이 브라우저에서는 음성 듣기 기능을 지원하지 않습니다.');
        }
    }

    function nextQuestion() {
        currentIndex++;
        loadQuestion();
    }

    function showReview() {
        document.getElementById('quiz-area').classList.add('hidden');
        document.getElementById('review-area').classList.remove('hidden');
        document.getElementById('main-title').innerText = "결과 및 오답 노트";

        const reviewList = document.getElementById('review-list');
        reviewList.innerHTML = '';

        if (starredQuestions.length === 0) {
            reviewList.innerHTML = `<div class="review-empty">🎉 어려운 문장이 없습니다! 완벽해요! 🎉</div>`;
        } else {
            starredQuestions.forEach((q, idx) => {
                let meaningHtml = (isPhrasalMode && q.meaning) ? `<div style="font-size: 13px; color: #b45309; background: #fef3c7; padding: 4px 8px; border-radius: 4px; display: inline-block; margin-bottom: 5px;">${q.meaning}</div>` : '';
                
                reviewList.innerHTML += `
                    <div class="review-card">
                        <div style="font-size: 12px; color: #94a3b8; margin-bottom: 5px;">${idx + 1}. 출처: ${q.source}</div>
                        ${meaningHtml}
                        <div class="review-ko">${q.ko}</div>
                        <div class="review-en">${q.en}</div>
                    </div>
                `;
            });
        }
    }

    function resetToHome() {
        document.getElementById('review-area').classList.add('hidden');
        document.getElementById('mode-selection').classList.remove('hidden');
        document.getElementById('main-title').innerText = "🚀 스피드 영어 퀴즈";
    }
</script>

</body>
</html>
