<template>
    <CCard>
        <CCardBody>
            <CRow>
                <CCol sm="5">
                    <h4 id="traffic" class="card-title mb-0">
                        나의 학습질문
                    </h4>
                    <div class="small text-muted">
                        .
                    </div>
                </CCol>
            </CRow>
            <CRow>
                <CCol col="12" sm="6" md="6">
                    <CCard>
                        <CCardHeader
                            @click="cardCollapse = !cardCollapse"
                            class="btn text-left"
                        >
                            <strong>첫번째 질문 제목입니다.</strong>
                        </CCardHeader>
                        <CCollapse :show="cardCollapse">
                            <CCardBody class="m-1">
                                {{ text }}
                            </CCardBody>
                        </CCollapse>
                    </CCard>
                </CCol>
                <CCol col="12" sm="6" md="6">
                    <CCard>
                        <CCardHeader
                            @click="cardCollapse = !cardCollapse"
                            class="btn text-left"
                        >
                            <strong>두번째 질문 제목입니다.</strong>
                        </CCardHeader>
                        <CCollapse :show="cardCollapse">
                            <CCardBody class="m-1">
                                {{ text }}
                            </CCardBody>
                        </CCollapse>
                    </CCard>
                </CCol>
            </CRow>
        </CCardBody>
    </CCard>
</template>
<script>
import { cilMediaPlay } from "@coreui/icons";
export default {
    cilMediaPlay,
    data() {
        return {
            collapse: false,
            cardCollapse: false,
            innerCollapse: false,
            text: `
        ㄹㄴ어리ㅏㄴ이ㅏ런이ㅏ런이러니아러
        ㄴ이런이ㅏㅓ리
        ㄴㅇㄹㄴ얼ㄴㅇ리ㅏㄴㅇ리ㅏㄴ어리ㅏㄴ어리ㅏ넝리ㅓㄴ이ㅏㄹㄴ얼
        ㄴㅇㄹ
        ㄴㅇ런ㅇ러니어란얼ㄴㄹ
      `,
        };
    },
    mounted() {},
    methods: {},
};
</script>
