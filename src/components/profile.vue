<template>
  <b-modal id="propfileModal" title="profile" size="lg" scrollable>
    <div>
      <img
        src="@/assets/profile.png"
        class="rounded mx-auto d-block"
        style="width: 240px; height: 320px"
      />
    </div>
    <div class="mt-2 mb-2 border border-primary rounded w-25 bg-primary">
      <h5 class="text-center text-white">
        {{ introduce }}
      </h5>
    </div>
    <div>
      <p>"어떻게 하면 사용자들의 불편함을 줄일수 있을까?"</p>
      <p>안녕하세요! 프론트엔드 주니어 개발자 장재혁입니다.</p>
      <p>
        고등학교때 친구의 소개로 우연히 접한 C 프로그래밍 시작으로 현재는 어떻게
        하면 사용자가 편하게 사용할 수 있을까? 라는 사용자의 관점을 고안하며
        개발하고 있습니다.
      </p>
      <p>
        아직 거창한 업무 성과보다 사용자의 작은 문제해결에 끝까지 몰입하는
        주니어 개발자입니다 이런 저의 성장가능성을 믿고 이끌어줄 회사를 찾고
        있습니다.
      </p>
    </div>
    <div class="border border-primary rounded w-25 bg-primary mb-2">
      <h5 class="text-center text-white">{{ techStack }}</h5>
    </div>
    <div>
      <h6>javaScript</h6>
      <b-progress
        :value="jsValue"
        show-value
        class="mb-3"
        striped
        :animated="animate"
      ></b-progress>
      <h6>Vue.js</h6>
      <b-progress
        :value="vueValue"
        show-value
        class="mb-3"
        striped
        :animated="animate"
      ></b-progress>
      <h6>TypeScript</h6>
      <b-progress
        :value="tsValue"
        show-value
        class="mb-3"
        striped
        :animated="animate"
      ></b-progress>
      <h6>cs</h6>
      <b-progress
        :value="csValue"
        show-value
        class="mb-3"
        striped
        :animated="animate"
      ></b-progress>
      <div class="border border-primary rounded w-25 bg-primary">
        <h5 class="text-white text-center">{{ timeLine }}</h5>
      </div>
      <div class="row border border-primary">
        <ul>
          <li>
            <small>2019.03</small>
            <div class="row border rounded">
              <h6>대림대학교 입학</h6>
              <p>융합소프트웨어과 19학번</p>
            </div>
          </li>
        </ul>
      </div>
      <div class="row">2</div>
      <div class="row">3</div>
      <div class="row">4</div>
    </div>
  </b-modal>
</template>
<script>
export default {
  name: "profile",
  methods: {},
  data() {
    return {
      timeLine: "<TimeLine />",
      techStack: "<TachStack />",
      introduce: "<Introduce />",
      jsValue: "70",
      vueValue: "60",
      tsValue: "50",
      csValue: "60",
      animate: true,
    };
  },
};
</script>
