### Hi there 👋

<!--
**kemerovo23alexey/kemerovo23alexey** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
импортировать  {  VKMiniAppAPI  }  из  "@vkontakte/vk-mini-apps-api" ;
импорт  {  сохранить  }  из  "../../index" ;
импортировать  {  setColorScheme  }  из  "../../store/data/actions" ;

const  api  =  новый  VKMiniAppAPI ( ) ;

экспортировать  константу  STORAGE_KEYS  =  {
  СТАТУС : "статус" ,
  ПРОСМОТР : "просмотрено" ,
} ;

экспортировать  const  initApp  =  ( )  =>  API . инициализировать приложение ( ) ;

апи . onUpdateConfig ( ( res )  =>  {
  если  ( раз . схема )  хранить . диспетчеризация ( setColorScheme ( рез . схема ) ) ;
} ) ;

экспортировать  константу getUserInfo =  ( ) = > {    
  вернуть  апи . получитьинформацию о пользователе ( ) ;
} ;

экспортировать  const  tapticNotification  =  ( type )  =>  {
  апи . мост . send ( "VKWebAppTapticNotificationOccurred" ,  { тип } ) ;
} ;

экспортировать  const  tapticSelectNotification  =  ( )  =>  {
  апи . мост . send ( "VKWebAppTapticSelectionChanged" ,  { } ) ;
} ;

экспортировать  константу isIntroViewed =  async ( ) = > {     
  возврат  ожидания  API . storageGet ( STORAGE_KEYS.STATUS ) ; _ _
} ;
экспортировать  константу setIntroViewed =  async ( ) = > {     
  апи . storageSet ( STORAGE_KEYS . STATUS ,  STORAGE_KEYS . VIEWED ) ;
} ;
