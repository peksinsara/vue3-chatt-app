<template>
  <div>
    <div :style="styles.wrapper">
      <div
        :key="i"
        :style="styles.component"
        class="kitchen-sink__component"
        v-for="(type, i) in Object.keys(components)"
      >
        <div
          :key="i"
          :style="styles.box"
          class="kitchen-sink__box"
          v-for="({ title, image, desc, href }, i) in components[type]"
        >
          <div :style="styles.titleWrapper">
            <div :style="styles.thumbnailWrapper">
              <comet-chat-avatar
                border-width="0px"
                :image="`images/${image}.png`"
              />
            </div>
            <h2 :style="styles.componentTitle">{{ title }}</h2>
          </div>
          <div :style="styles.descWrapper">
            <p v-html="desc"></p>
          </div>
          <ul :style="styles.linkWrapper" class="kitchen-sink__link__wrapper">
            <li>
              <a class="kitchen-sink__link" :style="styles.link" :href="href">
                Open the app
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <div :style="styles.logoutBtn">
      <button @click="logout" :style="styles.logoutBtn.button">Logout</button>
    </div>
    <div :style="{ height: '32px' }"></div>
  </div>
</template>

<script>
import { CometChat } from "@cometchat-pro/chat";
import { CometChatAvatar } from "../../cometchat-pro-vue-ui-kit/CometChatWorkspace/src";

import * as style from "./style";

export default {
  name: "AppNavigation",
  components: { CometChatAvatar },
  data() {
    return {
      components: {
        chatComponents: [
          {
            title: "Chatty",
            href: "/home",
            image: "rocket",
            desc: "Welcome to  <code>Chatty</code>",
          },
        ],
        screenComponents: [],
        listComponents: [],
      },
    };
  },
  created() {
    CometChat.getLoggedinUser().then(
      (user) => {
        if (!user) {
          location.href = "/";
        }
      },
      (error) => {
        console.log(error);
        location.href = "/";
      }
    );
  },
  computed: {
    styles() {
      return {
        wrapper: style.wrapperStyle(),
        title: style.titleStyle(),
        subTitle: style.subTitleStyle(),
        helpText: style.helpTextStyle(),
        component: style.componentStyle(),
        box: style.boxStyle(),
        titleWrapper: style.titleWrapperStyle(),
        thumbnailWrapper: style.thumbnailWrapperStyle(),
        componentTitle: style.componentTitleStyle(),
        descWrapper: style.descWrapperStyle(),
        linkWrapper: style.linkWrapperStyle(),
        link: style.linkStyle(),
        logoutBtn: style.logoutBtn(),
      };
    },
  },
  methods: {
    logout() {
      CometChat.logout().then(() => {
        location.href = "/";
      });
    },
  },
};
</script>
<style>
code {
  padding: 2px;
  font-size: 105%;
  color: crimson;
  border-radius: 4px;
  background-color: #f1f1f1;
}
</style>

<style scoped>
li {
  list-style-type: none;
}
.kitchen-sink__link {
  color: darken(rgb(67, 171, 255), 20%);
  font-weight: 600;
  font-size: 14px;
}
@media (min-width: 320px) and (max-width: 767px) {
  .kitchen-sink__title {
    font-size: 20px;
  }
  .kitchen-sink__subtitle {
    font-size: 16px;
  }
  .kitchen-sink__box {
    width: 400px;
  }
  .kitchen-sink__link__wrapper {
    flex-direction: column;
  }
  .kitchen-sink__link__wrapper li {
    padding: 10px;
  }
  .kitchen-sink__component {
    flex-direction: column;
    padding: 50px 100px;
  }
}
@media (min-width: 768px) and (max-width: 1024px) {
  .kitchen-sink__component {
    flex-direction: column;
    padding: 50px 50px;
  }
}
</style>