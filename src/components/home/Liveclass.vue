<template>
    <CCard>
        <CCardBody>
            <CRow>
                <CCol sm="5">
                    <h4 id="traffic" class="card-title mb-0">
                        라이브클래스
                    </h4>
                    <div class="small text-muted">&nbsp;-</div>
                </CCol>
            </CRow>
            <CRow>
                <template v-for="(obj, index) in list">
                    <CCol sm="6" md="4">
                        <CWidgetProgressIcon
                            :header="obj.title"
                            :text="
                                obj.onair
                                    ? '현재 방송중입니다.'
                                    : '방송중이 아닙니다.'
                            "
                            :color="obj.onair ? 'warning' : 'secondary'"
                            :value="obj.rate"
                        >
                            <CButton
                                :color="obj.onair ? 'warning' : 'secondary'"
                            >
                                <CIcon :content="$options.cilMediaPlay" />
                            </CButton>
                        </CWidgetProgressIcon>
                    </CCol>
                </template>
            </CRow>
            <!-- <CRow>
                <CCol sm="12" class="text-center">
                    <video
                        autoplay="true"
                        controls
                        src="http://eduwillpmp.nefficient.co.kr/eduwillpmp/eduwill/flv/globalCommecial/20180102/global_3.mp4"
                        width="100%"
                    ></video>
                </CCol>
            </CRow> -->
        </CCardBody>
    </CCard>
</template>
<script>
import { cilMediaPlay } from "@coreui/icons";
export default {
    cilMediaPlay,
    data() {
        return {
            list: [
                {
                    title: "서울 대방",
                    onair: true,
                    rate: 100,
                },
                {
                    title: "부산 서면",
                    onair: true,
                    rate: 100,
                },
                {
                    title: "경기 성남",
                    onair: true,
                    rate: 100,
                },
                {
                    title: "경기 일산",
                    onair: false,
                    rate: 0,
                },
                {
                    title: "대전",
                    onair: false,
                    rate: 0,
                },
                {
                    title: "서울 홍대",
                    onair: false,
                    rate: 0,
                },
            ],
        };
    },
    components: {},
    mounted() {},
    methods: {
        toKebabCase(str) {
            //console.log(str);
            //str = str.replace(/([a-z])([A-Z0-9])/g, "$1-$2").toLowerCase();
            //console.log(str);
            return str;
        },
        getIcon(iconName) {},
    },
};
</script>
