<template>
    <CRow>
        <CCol sm="6" lg="3">
            <CWidgetProgress
                header="출석"
                text="100%"
                footer="오늘도 열공"
                color="success"
                inverse
                :value="100"
            />
        </CCol>
        <CCol sm="6" lg="3">
            <CWidgetProgress
                header="학습시간"
                text="70%"
                footer="조금만 더 화이팅^^"
                color="info"
                inverse
                :value="70"
            />
        </CCol>
        <CCol sm="6" lg="3">
            <CWidgetProgress
                header="강의 수강"
                text="50%"
                footer="4강 남았습니다"
                color="warning"
                inverse
                :value="50"
            />
        </CCol>
        <CCol sm="6" lg="3">
            <CWidgetProgress
                header="문제풀이"
                text="100%"
                footer="목표 달성!"
                color="danger"
                inverse
                :value="100"
            />
        </CCol>
    </CRow>
</template>
