<template>
    <CCard>
        <CCardBody>
            <CRow>
                <CCol sm="5">
                    <h4 id="traffic" class="card-title mb-0">
                        나의 학습패턴
                    </h4>
                    <div class="small text-muted">
                        2020.06.01 ~ 2020.06.07
                    </div>
                </CCol>
                <CCol sm="7" class="d-none d-md-block">
                    <CButton color="primary" class="float-right">
                        <CIcon name="cil-cloud-download" />
                    </CButton>
                    <CButtonGroup class="float-right mr-3">
                        <CButton
                            color="outline-secondary"
                            v-for="(value, key) in ['Day', 'Month', 'Year']"
                            :key="key"
                            class="mx-0"
                            :pressed="value === selected ? true : false"
                            @click="selected = value"
                        >
                            {{ value }}
                        </CButton>
                    </CButtonGroup>
                </CCol>
            </CRow>
            <!-- <MainChartExample style="height:300px;margin-top:40px;" /> -->
            <CChartLine
                style="height:300px;margin-top:40px;"
                :datasets="defaultDatasets"
                :options="defaultOptions"
                :labels="['월', '화', '수', '목', '금', '토', '일']"
            />
        </CCardBody>
        <CCardFooter>
            <CRow class="text-center">
                <CCol md sm="12" class="mb-sm-2 mb-0">
                    <div class="text-muted">출석</div>
                    <strong>8일 (100%)</strong>
                    <CProgress
                        class="progress-xs mt-2"
                        :precision="1"
                        color="success"
                        :value="100"
                    />
                </CCol>
                <CCol md sm="12" class="mb-sm-2 mb-0 d-md-down-none">
                    <div class="text-muted">학습시간</div>
                    <strong>40시간 (30%)</strong>
                    <CProgress
                        class="progress-xs mt-2"
                        :precision="1"
                        color="info"
                        :value="30"
                    />
                </CCol>
                <CCol md sm="12" class="mb-sm-2 mb-0">
                    <div class="text-muted">강의수강</div>
                    <strong>38강 (60%)</strong>
                    <CProgress
                        class="progress-xs mt-2"
                        :precision="1"
                        color="warning"
                        :value="60"
                    />
                </CCol>
                <CCol md sm="12" class="mb-sm-2 mb-0">
                    <div class="text-muted">문제풀이</div>
                    <strong>140문항 (80%)</strong>
                    <CProgress
                        class="progress-xs mt-2"
                        :precision="1"
                        color="danger"
                        :value="80"
                    />
                </CCol>
            </CRow>
        </CCardFooter>
    </CCard>
</template>
<script>
import { CChartLine } from "@coreui/vue-chartjs";
import { getStyle, hexToRgba } from "@coreui/utils/src";

function random(min, max) {
    return Math.floor(Math.random() * (max - min + 1) + min);
}

export default {
    name: "MainChartExample",
    data() {
        return {
            selected: true,
        };
    },
    components: {
        CChartLine,
    },
    computed: {
        defaultDatasets() {
            const brandSuccess = getStyle("success2") || "#4dbd74";
            const brandInfo = getStyle("info") || "#20a8d8";
            const brandWarn = getStyle("warning") || "#f9b115";
            const brandDanger = getStyle("danger") || "#f86c6b";

            let elements = 10;
            const data1 = [];
            const data2 = [];
            const data3 = [];
            const data4 = [];

            for (let i = 0; i <= elements; i++) {
                data1.push(100);
                data2.push(random(80, 50));
                data3.push(random(80, 75));
                data4.push(65);
            }
            return [
                {
                    label: "출석",
                    backgroundColor: hexToRgba(brandSuccess, 10),
                    borderColor: brandSuccess,
                    pointHoverBackgroundColor: brandSuccess,
                    borderWidth: 2,
                    data: data1,
                },
                {
                    label: "학습시간",
                    backgroundColor: "transparent",
                    borderColor: brandInfo,
                    pointHoverBackgroundColor: brandInfo,
                    borderWidth: 2,
                    data: data2,
                },
                {
                    label: "강의수강",
                    backgroundColor: "transparent",
                    borderColor: brandWarn,
                    pointHoverBackgroundColor: brandWarn,
                    borderWidth: 2,
                    data: data3,
                },
                {
                    label: "문제풀이",
                    backgroundColor: "transparent",
                    borderColor: brandDanger,
                    pointHoverBackgroundColor: brandDanger,
                    borderWidth: 2,
                    data: data4,
                },
            ];
        },
        defaultOptions() {
            return {
                maintainAspectRatio: false,
                legend: {
                    display: false,
                },
                scales: {
                    xAxes: [
                        {
                            gridLines: {
                                drawOnChartArea: false,
                            },
                        },
                    ],
                    yAxes: [
                        {
                            ticks: {
                                beginAtZero: true,
                                maxTicksLimit: 10,
                                stepSize: Math.ceil(100 / 10),
                                max: 100,
                            },
                            gridLines: {
                                display: true,
                            },
                        },
                    ],
                },
                elements: {
                    point: {
                        radius: 0,
                        hitRadius: 10,
                        hoverRadius: 4,
                        hoverBorderWidth: 3,
                    },
                },
            };
        },
    },
};
</script>
