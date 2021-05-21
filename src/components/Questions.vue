<template>
    <div class="questions-ctr">
        <div class="progress">
            <div 
                class="bar" 
                :style="{ width: `${questionsAnswered / questions.length * 100}%` }"
            ></div>
            <div class="status">
                {{ questionsAnswered }} out of {{ questions.length }} questions answered
            </div>
        </div>
        <div 
            class="single-question"
            v-for="question in questions"
            :key="question.q"
        >
            <div class="question">{{ questions.q }}</div>
            <div class="answers">
                <div 
                    class="answer"
                    v-for="answer in question.answers"
                    :key="answer.text"
                >{{ answer.text }}</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['questions'],
}
</script>
