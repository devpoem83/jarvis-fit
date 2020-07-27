<template>
    <div>
        <Status />
        <Fattern />
        <Liveclass />
        <Sugang />
        <Quiz />
        <Qna />
    </div>
</template>

<script>
import Status from "../../components/home/Status";
import Fattern from "../../components/home/Fattern";
import Liveclass from "../../components/home/Liveclass";
import Sugang from "../../components/home/Sugang";
import Quiz from "../../components/home/Quiz";
import Qna from "../../components/home/Qna";

export default {
    name: "Home",
    components: {
        Status,
        Fattern,
        Liveclass,
        Sugang,
        Quiz,
        Qna,
    },
    data() {
        return {};
    },
    methods: {},
};
</script>
