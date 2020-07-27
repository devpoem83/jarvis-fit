<template>
    <CCard>
        <CCardBody>
            <CRow>
                <CCol sm="5">
                    <h4 id="traffic" class="card-title mb-0">
                        문제풀이
                    </h4>
                    <div class="small text-muted">
                        .
                    </div>
                </CCol>
            </CRow>
            <CRow>
                <template v-for="(obj, index) in list">
                    <CCol sm="6" md="6">
                        <CCard
                            :border-color="obj.isPosible == true ? 'info' : ''"
                        >
                            <CCardHeader>
                                {{ obj.title }}
                            </CCardHeader>
                            <CCardBody>
                                <p>응시기간 : {{ obj.period }}</p>
                                <CButton
                                    v-if="obj.isPosible == false"
                                    block
                                    color="dark"
                                    shape="pill"
                                    >응시불가</CButton
                                >
                                <CButton
                                    v-else-if="obj.isAttempt == false"
                                    block
                                    color="info"
                                    shape="pill"
                                    >응시하기</CButton
                                >
                                <CButton
                                    v-else-if="obj.isAttempt == true"
                                    block
                                    color="secondary"
                                    shape="pill"
                                    >응시완료</CButton
                                >
                            </CCardBody>
                        </CCard>
                    </CCol>
                </template>
                <!-- <CCol sm="6" md="6">
                    <CCard>
                        <CCardHeader>
                            데일리테스트
                        </CCardHeader>
                        <CCardBody>
                            <p>응시기간 : 2020.06.01 ~ 2020.06.30</p>
                            <CButton block color="secondary" shape="pill"
                                >응시완료</CButton
                            >
                        </CCardBody>
                    </CCard>
                </CCol>
                <CCol sm="6" md="6">
                    <CCard>
                        <CCardHeader>
                            모의고사
                        </CCardHeader>
                        <CCardBody>
                            <p>응시기간 : 2020.06.01 ~ 2020.06.30</p>
                            <CButton block color="secondary" shape="pill"
                                >응시완료</CButton
                            >
                        </CCardBody>
                    </CCard>
                </CCol> -->
            </CRow>
        </CCardBody>
    </CCard>
</template>
<script>
export default {
    data() {
        return {
            list: [
                {
                    title: "3분영어퀴즈",
                    period: "2020.06.01 ~ 2020.06.30",
                    isPosible: true,
                    isApply: true,
                    isAttempt: false,
                },
                {
                    title: "데일리테스트",
                    period: "2020.06.01 ~ 2020.06.30",
                    isPosible: true,
                    isApply: true,
                    isAttempt: true,
                },
                {
                    title: "모의고사",
                    period: "2020.06.01 ~ 2020.06.30",
                    isPosible: false,
                    isApply: false,
                    isAttempt: false,
                },
            ],
        };
    },
    mounted() {},
    methods: {},
};
</script>
