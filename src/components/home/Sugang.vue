<template>
    <CCard>
        <CCardBody>
            <CRow>
                <CCol sm="5">
                    <h4 id="traffic" class="card-title mb-0">
                        강의 수강
                    </h4>
                    <div class="small text-muted">
                        .
                    </div>
                </CCol>
                <CCol sm="12">
                    <CCardBody>
                        <CDataTable
                            :hover="true"
                            :striped="striped"
                            :bordered="bordered"
                            :small="small"
                            :fixed="fixed"
                            :items="items"
                            :fields="fields"
                            :items-per-page="small ? 10 : 5"
                            :dark="dark"
                            pagination
                        >
                            <td slot="product" slot-scope="{ item }">
                                <div>{{ item.product.title }}</div>
                            </td>
                            <td slot="course" slot-scope="{ item }">
                                {{ item.course.title }}
                            </td>
                            <td slot="lecture" slot-scope="{ item }">
                                {{ item.lecture.title }}
                                <CProgress
                                    class="progress-xs"
                                    v-model="item.lecture.rate"
                                    :color="color(item.lecture.rate)"
                                />
                            </td>
                            <td slot="isComplete" slot-scope="{ item }">
                                <CButton
                                    v-if="item.isComplete"
                                    color="default"
                                    shape="pill"
                                    >수강완료</CButton
                                >
                                <CButton
                                    v-if="!item.isComplete"
                                    color="success"
                                    shape="pill"
                                    >수강하기
                                    <CIcon :content="$options.cilMediaPlay"
                                /></CButton>
                            </td>
                        </CDataTable>
                    </CCardBody>
                </CCol>
            </CRow>
        </CCardBody>
    </CCard>
</template>
<script>
import { cilMediaPlay } from "@coreui/icons";
export default {
    cilMediaPlay,
    name: "Table",
    data() {
        return {
            items: [
                {
                    product: {
                        code: "123456",
                        title: "9급공무원 평생회원반",
                    },
                    course: {
                        code: "dfsdfsd",
                        title: "국어 기초이론",
                    },
                    lecture: {
                        code: 1,
                        title: "1강",
                        rate: 95,
                    },
                    isComplete: true,
                },
                {
                    product: {
                        code: "123456",
                        title: "9급공무원 평생회원반",
                    },
                    course: {
                        code: "dfsdfsd",
                        title: "국어 기초이론",
                    },
                    lecture: {
                        code: 2,
                        title: "2강",
                        rate: 90.5,
                    },
                    isComplete: true,
                },
                {
                    product: {
                        code: "123456",
                        title: "9급공무원 평생회원반",
                    },
                    course: {
                        code: "dfsdfsd",
                        title: "국어 기초이론",
                    },
                    lecture: {
                        code: 3,
                        title: "3강",
                        rate: 100.0,
                    },
                    isComplete: true,
                },
                {
                    product: {
                        code: "123456",
                        title: "9급공무원 평생회원반",
                    },
                    course: {
                        code: "dfsdfsd",
                        title: "국어 기초이론",
                    },
                    lecture: {
                        code: 4,
                        title: "4강",
                        rate: 0,
                    },
                    isComplete: false,
                },
                {
                    product: {
                        code: "123456",
                        title: "9급공무원 평생회원반",
                    },
                    course: {
                        code: "dfsdfsd",
                        title: "국어 기초이론",
                    },
                    lecture: {
                        code: 5,
                        title: "5강",
                        rate: 0,
                    },
                    isComplete: false,
                },
            ],
            fields: ["product", "course", "lecture", "isComplete"],
            caption: {
                type: "",
                default: "Table",
            },
            hover: true,
            striped: true,
            bordered: true,
            small: true,
            fixed: true,
            dark: false,
        };
    },
    mounted() {
        //this.items = this.getSugangData();
    },
    methods: {
        getBadge(isComplete) {
            return isComplete === true ? "success" : "secondary";
        },

        getStatus(isComplete) {
            return isComplete === true ? "완료" : "대기";
        },

        color(value) {
            var color;
            if (value <= 25) {
                color = "danger";
            } else if (value > 25 && value <= 50) {
                color = "warning";
            } else if (value > 50 && value <= 75) {
                color = "info";
            } else if (value > 75 && value <= 100) {
                color = "success";
            }
            return color;
        },
    },
};
</script>
