Denys Ivaschenko, [02.03.2025 23:15]
<script setup>
import { ref, computed } from 'vue';
import logo from './assets/HelpStud.png';
import sideImage from './assets/cfu.png';
import searchIcon from './assets/search-icon.png';

// Импортируем изображения для предметов
import algorithmsImage from './assets/sub/algorithm.png';
import communicationImage from './assets/sub/communication.png';
import historyImage from './assets/sub/history.png';
import infProg from './assets/sub/infProg.png';
import math from './assets/sub/math.png';
import eng from './assets/sub/eng.png';
import programming from './assets/sub/programming.png';
import sport from './assets/sub/sport.png';
import doProject from './assets/sub/doProject.png';


import os from './assets/sub/os.png';
import methodV from './assets/sub/methodV.png';
import stp from './assets/sub/stp.png';
import osrf from './assets/sub/osrf.png';
import perPr from './assets/sub/perPr.png';
import zifrTech from './assets/sub/zifrTech.png';
import ecoresh from './assets/sub/ecoresh.png';


import compNet from './assets/sub/compNet.png';
import objP from './assets/sub/objP.png';
import mathVer from './assets/sub/mathVer.png';
import intAn from './assets/sub/intAn.png';
import osnProject from './assets/sub/osnProject.png';
import bezPr from './assets/sub/bezPr.png';


import ziftFuture from './assets/sub/ziftFuture.png';
import desMath from './assets/sub/desMath.png';
import mkm from './assets/sub/mkm.png';
import authmath from './assets/sub/authmath.png';
import bd from './assets/sub/bd.png';
import hisRel from './assets/sub/hisRel.png';

import fizika from './assets/sub/fizika.png';
import praktTheory from './assets/sub/praktTheory.png';
import iskIntel from './assets/sub/iskIntel.png';
import compSys from './assets/sub/compSys.png';
import sysProg from './assets/sub/sysProg.png';
import signal from './assets/sub/signal.png';
import microProc from './assets/sub/microProc.png';
import sysAdm from './assets/sub/sysAdm.png';
import devProj from './assets/sub/devProj.png';
import verif from './assets/sub/verif.png';
import parDist from './assets/sub/parDist.png';
import techPr from './assets/sub/techPr.png';
import elektro from './assets/sub/elektro.png';
import projInfSys from './assets/sub/projInfSys.png';
import infSec from './assets/sub/infSec.png';
import infoCod from './assets/sub/infoCod.png';
import militPrep from './assets/sub/militPrep.png';
import projProg from './assets/sub/projProg.png';


import progModel from './assets/sub/progModel.png';
import netTel from './assets/sub/netTel.png';
import globNet from './assets/sub/globNet.png';
import commNet from './assets/sub/commNet.png';
import humanIntf from './assets/sub/humanIntf.png';
import crossPlat from './assets/sub/crossPlat.png';
import webPr from './assets/sub/webPr.png';
import mobileApp from './assets/sub/mobileApp.png';


const searchQuery = ref('');
const selectedSubject = ref(null);
const isModalOpen = ref(false);




// Массив предметов с данными
const subjects = [
  { 
    name: "Структуры и алгоритмы обработки данных", 
    description: "Изучение структур данных и алгоритмов их обработки.", 
    image: algorithmsImage, 
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1qPaEi3TdbSK3M3f81P7KutIDX8EsRlhjX4f4AQD2-xk/edit?usp=sharing" 
  },
  { 
    name: "Деловая коммуникация и русская речевая культура", 
    description: "Развитие навыков делового общения и культуры речи.", 
    image: communicationImage, 
    fearRating: 3,
    docLink: "https://docs.google.com/document/d/15aRhSYUqKa8aDya5p3YuTuugEsvD8xcY9B8qnkDbAgQ/edit?usp=sharing" // Замените на реальную ссылку
  },
  { 
    name: "История России", 
    description: "Изучение ключевых событий и процессов в истории России.", 
    image: historyImage, 
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1kDTU-cg00oGQx7KHdcmJsKeyr5__mjsALOwDi0xkP8s/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name: "Информатика и основы программирования",
    description: "Изучение основ программирования и применения информационных технологий в различных областях.",
    image: infProg,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1CwM3E22gRBwyQhmNyn-0mBzX7H6mDOcO7BJmZ8l9qkg/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Высшая математика",
    description:"Изучение высших курсов математики и их применения в различных областях.",
    image: math,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/1tUqpIeMJKvRXvjjfdHttUoNqorMgsFgI3rLAlCObUo0/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Иностранные языки",
    description:"Изучение иностранных языков и их применения в различных областях.",
    image: eng,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/1oeJ9_O8G6BmYrQJsvxh9Q7TMFypF6gxpcNIJQS3nAGw/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Алгоритмизация и программирование",
    description:"Изучение алгоритмов и программирования в различных областях.",
    image: programming,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/1raSPMqcdTfEua-QWGiRMotopW2o6RSSazsyH157MzWE/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Физическая культура и спорт",
    description:"Развитие физических навыков и умений в различных областях.",
    image: sport,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/14H13_EQId6Dg7im2y2EyemdpTCfg3uKt6TyoXkB62Tk/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Проектная деятельность",
    description:"Развитие навыков проектной деятельности",
    image: doProject,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/17onhBwlFmlnp4HvMKeDZ72mvCF1inSR8nLV2j2jDrzU/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Операционные системы",
    description:"Изучение операционных систем и их применения",
    image: os,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/169xwFQKP5p2aGB9XjtI3HeNxN5SYb9fviNNiGzOJ6FY/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Алгоритмы и методы вычислений",
    description:"Изучение алгоритмов и методов вычислений",
    image: methodV,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/1SAA8tn0-0VpLALzzoG89vGZRLSjrX3DbTyLQjGIgIkI/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Современне технологии программирования",
    description:"Изучение современных технологий программирования, таких как Git и другие. ",
    image: stp,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1ztfB74J6GG6opxyRxyAGakD6MCKhd-ExwDLHsjd_SCU/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Основы российской государственности",
    description:"Изучение основ российской государственности, включая её историю, права и системы управления властью.",
    image: osrf,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1kGynKlNpPyo1oFEVYaSDM6uCvr-pHBMrWbaK3EjQAho/edit?usp=sharing" // Замените на реальную ссылку




  },
  {
    name:"Человек и право",
    description:"Изучение прав человека и их особенностей.",
    image: perPr,
    fearRating: 4,    
    docLink: "https://docs.google.com/document/d/1GoQSyGgEzAknWqs1RzCvXOrGnGFhXUoPw8scHXbYiyU/edit?usp=sharing" // Замените на реальную ссылку
  },

  {
    name:"Цифровые технологии в профессиональной среде",
    description:"Изучение цифровых технологий в профессиональной среде.",
    image: zifrTech,
    fearRating: 2,
    docLink: "https://docs.google.com/document/d/1OQK-1hhTx_xXdxwBiDrgztWSwNJva3UGsHqvkrVqQs8/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Экономика личных решений",
    description:"Изучение экономики, принятие решений и процессы в области экономики.",
    image: ecoresh,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1J27-_254aMOAtrdDVrcTAEhE282jYKzb9FQE7SF49Sw/edit?usp=sharing" // Замените на реальную ссылку
  },

  {
    name:"Компьютерные сети",
    description:"Изучение компьютерных сетей и их применения.",
    image: compNet,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1rV6Sffd3lDDAZEuvGKwW38Sy6oIDxENJ2vQrqAMsl_E/edit?usp=sharing" // Замените на реальную ссылку

  },
  {
    name:"Объектно-ориентированное программирование",
    description:"Изучение объектно-ориентированного программирования на C#.",
    image: objP,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1B58KSFBE5bG0uz6sQpyCiRQK2euf9tTNb7DtonG-DlI/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Теория вероятностей и математическая статистика",
    description:"Изучение теории вероятностей и математической статистики.",
    image: mathVer,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1AigYgxJBIyr-2R9PypW5Oo7704TURv2mECRtHUYF7Sg/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Интеллектуальный анализ данных",
    description:"Изучение интеллектуального анализа данных и его применения. Также, искуственный интеллект.",
    image: intAn,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1QB_ZcpaOs6CJLa9qYKdPg1_8tH9wKC9fgG3A09PjlFY/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Основы социального проектирования",
    description:"Изучение основ социального проектирования и его применения.Проекты на социальном пространстве.",
    image: osnProject,
    fearRating: 3,
    docLink: "https://docs.google.com/document/d/1nHlk0dWxQ__XRtsM6d9jMVkmlR_110VakfP6U6VlopE/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Безопасность природной среды и жизнедеятельности человека",
    description:"Изучение безопасности природной среды и жизнедеятельности человека.Развитие навыков медицины",
    image: bezPr,
    fearRating: 4,    
    docLink: "https://docs.google.com/document/d/10mB_yeoGLeAXGlneVvPGdb8PSgS0KMllUi1JPYy4esM/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Цифровая экосистема будущего",
    description:"Изучение технологий и процессов в области цифровой экосистемы будущего.",
    image: ziftFuture,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1aXgyg9OBhIHDs-YYWhkOMLlVXJ0rHIe7O-byCbcTDH4/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Дискретная математика",
    description:"Изучение дискретной математики и ее применения.",
    image: desMath,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/1n2UOojHktWo9nWeD4F-dplNKVBz6uHn9wS64sLMDVRo/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Математическое и компьютерное моделирование",
    description:"Изучение математического и компьютерного моделирования,создание игр.",
    image: mkm,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/1-H1Z_FCGFzcMKfy1Tr4q16JPXJh1jWiWapzRVFkrM0s/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Теория автоматов и формальных языков",
    description:"Изучение теории автоматов и формальных языков.Также,изучение алгоритмов.",
    image: authmath,
    fearRating: 5,



    docLink: "https://docs.google.com/document/d/1Wfd7KQVctchAAwQxhyg1jUBrFMh4b8qSRv9T96mFgDc/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Базы данных",
    description:"Изучение баз данных и ее применения.",
    image: bd,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/12eOMhJ3Jy-mEbh-epzXrEYpsYXEKtJ9YG_lX7lLJ3os/edit?usp=sharing" // Замените на реальную ссылку
  },

  {
    name:"История религий России",
    description:"Изучение истории религий России. Как все зараждалось,а также,современное религиозное общество.",
    image: hisRel,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1hf5AJG1ZBJTAOJlEmenjeSYrzJvS4tc030dtffH7GOc/edit?usp=sharing" // Замените на реальную ссылку
  },
  {
    name:"Физика",
    description:"Изучение физики и ее применения в различных областях.",
    image: fizika,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/19ATssMAwgsWgbtq6unaQb3vo1FTMSz3FNK8-MtBnDt0/edit?usp=sharing"
  },
  {
    name:"Прикладная теория цифровых автоматов",
    description:"Изучение прикладной теории цифровых автоматов и ее применения.",
    image: praktTheory,
    fearRating: 5,
    docLink:"https://docs.google.com/document/d/1NWSlgPGBIkAUkGtcWZiCEbYwX7Fc784WW5Yr8Z_Ott8/edit?usp=sharing"
  },
  {
    name:"Искусственный интеллект: технологии и человек",
    description:"Изучение искусственного интеллекта, технологий и человека.",
    image: iskIntel,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1Ju_3X4r2sAGoDwOPFsWcUVof0KHw1NhX5mfQWGDb9pc/edit?usp=sharing"
  },
  {
    name:"Компьютерные системы",
    description:"Изучение компьютерных систем и их применения.",
    image: compSys,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1dZv1xrUIc46rtJ3rGXsP13vTLhRzGrPtApbBJw42Rgk/edit?usp=sharing"
  },
  {
    name:"Системное программное обеспечение",
    description:"Изучение системного программного обеспечения и его применения.",
    image: sysProg,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/1bRR-bnt6aROI3lot51PgEcWpzn6lJI-tNdSNItYax_w/edit?usp=sharing"
  },
  {
    name:"Обработка сигналов",
    description:"Изучение обработки сигналов и ее применения.",
    image: signal,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/1EbaWsD7pp9x6icI7mhPkJOb4SEHiV0h-ApSZsFGtN6E/edit?usp=sharing"
  },
  {
    name:"Микропроцессорные системы",
    description:"Изучение микропроцессорных систем и их применения.",
    image: microProc,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1b6M62cVXGO1aEIjtaAmwpsv0CFj4j4pLHQdORNxTvb4/edit?usp=sharing"
  },
  {
    name:"Системное администрирование",
    description:"Изучение системного администрирования и его применения.",
    image: sysAdm,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1hbALgQGMJK6mufPgVkt0PEmmvxXkSe2QgwAcsoZlL0U/edit?usp=sharing"
  },
  {
    name:"Управление разработкой командных программных проектов",
    description:"Изучение управления разработкой командных программных проектов и его применения.",
    image: devProj,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1gwtA-1xMmTMfydB1fdbsstY2i7lhIUb94nXZ2ZVOgzs/edit?usp=sharing"
  },
  {
    name:"Верификация, аттестация и качество программного обеспечения",
    description:"Изучение верификации, аттестации и качества программного обеспечения и его применения.",
    image: verif,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1VCwHZfSz_-UXqUMniBcKBNojt3cYQrtTuM5EiQ8ji7o/edit?usp=sharing"
  },
  {
    name:"Параллельные и распределенные вычисления",
    description:"Изучение параллельных и распределенных вычислений и их применения.",
    image: parDist,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1GuBsVuxE9-R_J66Hguw4al18XBivd5iKIKm441xqboc/edit?usp=sharing"
  },
  {
    name:"Технологии и процесс разработки программного обеспечения",
    description:"Изучение технологий и процесса разработки программного обеспечения и его применения.",
    image: techPr,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1fdsFhjZY7p_wpw-0dEmz6Y6uYxF6XQdF76DoCAxush4/edit?usp=sharing"
  },




  {
    name:"Электроника",
    description:"Изучение электроники и ее применения.",
    image: elektro,
    fearRating: 5,
    docLink: "https://docs.google.com/document/d/1ofqQe27oNEyLe8WsKJrv3tDKcNYmYDtF8C2M6Dryiq0/edit?usp=sharing"
  },

  {
    name:"Проектирование информационных систем",
    description:"Изучение проектирования информационных систем и ее применения.",
    image: projInfSys,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/170T0UGKBnortwpKPki4XdXaU7RO6JmSY2q5swlYAflQ/edit?usp=sharing"
  },

  {
    name:"Системное программирование",
    description:"Изучение системного программирования и его применения.",
    image: sysProg,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1uIrpNbEHQ6WuOYjyvpf6GVqObpFwlix-VdLyDK3eoXs/edit?usp=sharing"
  },

  {
    name:"Основы информационной безопасности",
    description:"Изучение основ информационной безопасности и ее применения.",
    image: infSec,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/197-5yLyJWWKHS5_JvLSkxu70xwNrNpriBlRKesu8YS8/edit?usp=sharing"
  },

  {
    name:"Теория информации и кодирование",
    description:"Изучение теории информации и кодирования и их применения.",
    image: infoCod,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1BOA3C73Se7quLjh6bHst0p340II5jk_OARCazWPCTzY/edit?usp=sharing"
  },

  {
    name:"Сети и телекоммуникации",
    description:"Изучение сетей и телекоммуникаций и их применения.",
    image: netTel,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/12OnG3HZ1BYurHxYHXaoOJpGx0raeIoOXAyZCd5VnD7c/edit?usp=sharing"
  },

  {
    name:"Web-программирование",
    description:"Изучение web-программирования и его применения.",
    image: webPr,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1QQ5MbByClCSTXDTUK3ZloUMIz9AuWomjVA11j68-Zek/edit?usp=sharing"
  },

  {
    name:"Основы военной подготовки",
    description:"Изучение основ военной подготовки и ее применения.",
    image: militPrep,
    fearRating: 3,
    docLink: "https://docs.google.com/document/d/1v2nFZBwfWEHuo2eklx0YY7q2r80h5Evxmbma1hkbL58/edit?usp=sharing"
  },

  {
    name:"Проектирование программного обеспечения",
    description:"Изучение проектирования программного обеспечения и его применения.",
    image: projProg,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1EAq_9yJLVJ539kR5uADfD3Fzse1buBYrAFKKW65Itxc/edit?usp=sharing"
  },

  {
    name:"Парадигмы программирования",
    description:"Изучение парадигм программирования и ее применения.",
    image: progModel,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/15oMLYJ6CVWj4_UIxXQJHkVEvF7jI48yiwag91BQoSa8/edit?usp=sharing"
  },
  {
    name:"Безопасность компьютерных сетей",
    description:"Изучение безопасности компьютерных сетей и ее применения.",
    image: compNet,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/10rKCPEEwVOv6pDbxsKZxOPU5YU7H0clCtnOyhCM3Cog/edit?usp=sharing"
  },
  {
    name:"Технологии проектирования сетей класса SOHO",
    description:"Изучение технологий проектирования сетей класса SOHO и ее применения.",
    image: netTel,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1-hWDaCgIg386qjNFR3VuiCJrotAwgPEm0V96rOx8-go/edit?usp=sharing"
  },
  {
    name:"Основы построения глобальных сетей",
    description:"Изучение основ построения глобальных сетей и ее применения.",
    image: globNet,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/113Lu_l9U3Qp3sXCvRLpllftsi4Nupp10I1q9f9Z5Jvw/edit?usp=sharing"
  },
  {
    name:"Основы коммутации в компьютерных сетях",
    description:"Изучение основ коммутации в компьютерных сетях и ее применения.",
    image: commNet,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1wbkZDzj_hBonGet-ceMGEOLhdkP3dGN5wXxDPYd8CV4/edit?usp=sharing"
  },




  {
    name:"Разрабокта и программирование человеко-машинного интерфейса",
    description:"Изучение разработки и программирования человеко-машинного интерфейса и его применения.",
    image: humanIntf,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1Cm33M61V51wmvFCQDRSsvyAwRM4FNtkSaeOlzh6X0O0/edit?usp=sharing"
  },
  {
    name:"Кроссплатформенное программирование",
    description:"Изучение кроссплатформенного программирования и его применения.",
    image: crossPlat,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1_Maz4MurMJLcQbtr1ma_xm3PotlhT3D4W0HAyu6FAKc/edit?usp=sharing"
  },
  {
    name:"Проектирование Web-приложений",
    description:"Изучение проектирования Web-приложений и его применения.",
    image: webPr,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/14OTNEpngsh-t4-ig3DIMtbDqtwHyfSNWUn22gcdsKhM/edit?usp=sharing"
  },
  {
    name:"Разработка мобильных приложений",
    description:"Изучение разработки мобильных приложений и его применения.",
    image: mobileApp,
    fearRating: 4,
    docLink: "https://docs.google.com/document/d/1OSU60SWu3fb2-RKB496QsrwrdJn9_N1pN2zMbO6qoDY/edit?usp=sharing"
  }
];

const filteredSubjects = computed(() => {
  if (!searchQuery.value) return [];
  return subjects.filter(subject =>
    subject.name.toLowerCase().includes(searchQuery.value.toLowerCase())
  );
});

const selectSubject = (subject) => {
  selectedSubject.value = subject;
  isModalOpen.value = true;
  searchQuery.value = '';
};

const closeModal = () => {
  isModalOpen.value = false;
  selectedSubject.value = null;
};
</script>

<template>
  <div class="page-container">
    <div class="header">
      <img :src="logo" alt="HelpStud Logo" class="logo" />
      <h1 class="title">HelpStud</h1>
      <div class="search-container">
        <div class="search-input-wrapper">
          <img :src="searchIcon" alt="Search" class="search-icon" />
          <input
            v-model="searchQuery"
            type="text"
            placeholder="Поиск предмета..."
            class="search-input"
          />
        </div>
        <div v-if="filteredSubjects.length > 0" class="suggestions">
          <div
            v-for="subject in filteredSubjects"
            :key="subject.name"
            class="suggestion-item"
            @click="selectSubject(subject)"
          >
            {{ subject.name }}
          </div>
        </div>
      </div>
    </div>

    <div class="content">
      <div class="str">
        <h2 class="about-heading">О нас</h2>
        <div class="text-with-image">
          <div class="text">
            <p>
              Университет — это важный шаг во взрослую жизнь, где ты найдёшь друзей, знания и начнёшь строить своё будущее.
            </p>
            <p class="subjects">
              HelpStud создан, чтобы помочь тебе в обучении по направлениям: <b>Программная инженерия, Информатика и вычислительная техника, Компьютерная безопасность и другим.</b>
            </p>
            <p>
              Используй <strong>поисковик</strong>, чтобы найти советы, ответы на вопросы и учебные материалы по нужному предмету. <b>Просто введи название — и получи результат!</b>
            </p>
            <p>
              Начни учиться уже сейчас и достигай своих целей быстрее!
            </p>
            <p>
              Развивайся и учись вместе с <b>HelpStud</b>!
            </p>
          </div>
          <img :src="sideImage" alt="CFU Image" class="side-image" />
        </div>
      </div>
    </div>




    <div v-if="isModalOpen" class="modal-overlay">
      <div class="modal">
        <button class="close-button" @click="closeModal">×</button>
        <div class="modal-content">
          <img :src="selectedSubject.image" alt="Subject Image" class="subject-image" />
          <div class="modal-text">
            <h2>{{ selectedSubject.name }}</h2>
            <p>{{ selectedSubject.description }}</p>
            <div class="fear-rating">
              <span>Рейтинг страха: </span>
              <span v-for="star in 5" :key="star" class="star" :class="{ 'filled': star <= selectedSubject.fearRating }">★</span>
            </div>
            <a 
              :href="selectedSubject.docLink" 
              target="_blank" 
              class="doc-link"
            >
              Открыть учебные материалы
            </a>
          </div>
        </div>
      </div>
    </div>

    <footer class="footer">
      <div class="footer-content">
        <div class="footer-section">
          <h3 class="footer-heading">Связь с нами</h3>
          <ul class="contact-list">
            <li>
              <a href="https://t.me/helpstud" target="_blank" class="contact-link">Telegram</a>
            </li>
          </ul>
        </div>
        <div class="footer-section right-section">
          <p>&copy; 2025 HelpStud.</p>
          <p>
            Разработано <a href="https://github.com/Metelykx" target="_blank" class="metelykx-link" id="links">Metelykx</a>
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>

<style>
body {
  background: #181818;
  margin: 0;
  font-family: 'Kanit', sans-serif;
  color: #ffffff;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>

<style scoped>
.page-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  background: #181818;
  color: #ffffff;
}

.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: 80px;
  position: fixed;
  top: 0;
  left: 0;
  background-color: #007bff;
  padding: 10px 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out forwards;
}

.logo {
  width: 50px;
  height: auto;
  margin-right: 15px;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.2s forwards;
}

.title {
  font-size: 25px;
  font-weight: bold;
  color: #ffffff;
  margin-right: auto;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.3s forwards;
}

.search-container {
  position: relative;
  margin-left: 20px;
  width: 300px;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.4s forwards;
}

.search-input-wrapper {
  display: flex;
  align-items: center;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 25px;
  padding: 8px 15px;
  transition: background-color 0.3s, box-shadow 0.3s;
}

.search-input-wrapper:hover {
  background-color: rgba(255, 255, 255, 0.2);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.search-icon {
  width: 20px;
  height: 20px;
  margin-right: 10px;
  filter: brightness(0) invert(1);
}

.search-input {
  flex: 1;
  background: transparent;
  border: none;
  outline: none;
  color: #ffffff;
  font-size: 16px;
  font-family: 'Kanit', sans-serif;
}

.search-input::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.suggestions {
  position: absolute;
  top: 100%;
  left: 0;
  right: 0;
  background: #333;
  border: 1px solid #444;
  border-radius: 4px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  max-height: 200px;
  overflow-y: auto;
}

.suggestion-item {
  padding: 10px;
  cursor: pointer;
  transition: background-color 0.2s;
  color: #ffffff;
}

.suggestion-item:hover {
  background-color: #444;
}

.content {
  flex: 1;
  padding-top: 100px;
  width: 100%;
  box-sizing: border-box;
}




.str {
  font-family: 'Kanit', sans-serif;
  color: #ffffff;
  line-height: 1.6;
  width: 100%;
  max-width: 1200px;
  padding: 30px;
  font-size: 20px;
  text-align: justify;
  margin: 20px auto 40px;
  border-radius: 20px;
  background: #181818;
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.4s forwards;
}

.about-heading {
  font-size: 30px;
  font-weight: bold;
  color: #007bff;
  font-family: 'Kanit', sans-serif;
  margin: 20px 0;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.5s forwards;
}

.text-with-image {
  display: flex;
  align-items: flex-start;
  gap: 100px;
  width: 100%;
}

.text {
  flex: 1;
  max-width: 800px;
  min-width: 600px;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.6s forwards;
}

.side-image {
  width: 400px;
  height: auto;
  margin-top: 0;
  flex-shrink: 0;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.7s forwards;
}

.str p {
  margin-bottom: 20px;
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1001;
}

.modal {
  background: #181818;
  padding: 20px;
  border-radius: 8px;
  max-width: 600px;
  width: 90%;
  position: relative;
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}

.modal-content {
  display: flex;
  align-items: flex-start;
  gap: 20px;
}

.subject-image {
  width: 150px;
  height: auto;
  border-radius: 8px;
  flex-shrink: 0;
}

.modal-text {
  flex: 1;
}

.modal h2 {
  color: #007bff;
  margin-bottom: 10px;
  font-size: 24px;
}

.modal p {
  color: #ffffff;
  font-size: 16px;
  line-height: 1.6;
  margin-bottom: 15px;
}

.fear-rating {
  display: flex;
  align-items: center;
  margin-top: 10px;
}

.fear-rating .star {
  color: #ccc;
  font-size: 20px;
  cursor: pointer;
  transition: color 0.2s;
}

.fear-rating .star.filled {
  color: #ffcc00;
}

.doc-link {
  display: inline-block;
  background: #007bff;
  color: white;
  padding: 10px 20px;
  border-radius: 25px;
  text-decoration: none;
  margin-top: 15px;
  transition: background 0.3s ease;
  font-weight: 500;
  border: 2px solid transparent;
}

.doc-link:hover {
  background: #0056b3;
  border-color: rgba(255, 255, 255, 0.2);
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}

.close-button {
  position: absolute;
  top: 10px;
  right: 10px;
  background: none;
  border: none;
  font-size: 24px;
  cursor: pointer;
  color: #007bff;
}

.close-button:hover {
  color: #0056b3;
}

.footer {
  background-color: #181818;
  color: #7d7d7d;
  padding: 8px 20px;
  font-family: 'Kanit', sans-serif;
  margin-top: auto;
  text-align: center;
  border-top: 1px solid #8b8b8b;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  opacity: 0;
  animation: fadeIn 0.5s ease-in-out 0.8s forwards;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  width: 100%;
  max-width: 1200px;
  margin-bottom: 8px;
  gap: 10px;
}

.footer-section {
  flex: 1;
  margin: 0;
}

.footer-heading {
  font-size: 15px;
  font-weight: bold;
  color: #007bff;
}

.contact-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.contact-list li {
  margin-bottom: 4px;
}

.contact-link,
.metelykx-link {
  color: #7d7d7d;
  text-decoration: none;
  transition: color 0.3s;
  font-size: 15px;
}

.contact-link:hover,
.metelykx-link:hover {
  color: #007bff;
  text-decoration: underline;
}

#links {
  color: #007bff;
}

/* Медиа-запросы для адаптивности */

/* Медиа-запросы для адаптивности */
@media (max-width: 768px) {
  .header {
    flex-direction: column;
    height: auto;
    padding: 10px;
  }

  .logo {
    margin-bottom: 10px;
    display: none;
  }

  .title {
    font-size: 20px;
    margin-bottom: 20px;
    margin:0 auto;
  }

  .search-container {
    width: 100%;
    margin-left: 0;
  }

  .search-input-wrapper {
    width: 100%;
  }



  .content {
    padding-top: 150px;
  }

  .str {
    padding: 20px;
    font-size: 16px;
    margin-top:-10px;
  }

  .text-with-image {
    flex-direction: column;
    gap: 20px;
  }

  .text {
    min-width: unset;
    max-width: 100%;
  }

  .side-image {
    width: 100%;
    max-width: 300px;
    margin: 0 auto;
  }

  .modal {
    width: 95%;
    padding: 15px;
  }

  .modal-content {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .subject-image {
    width: 100%;
    max-width: 200px;
    margin-bottom: 20px;
  }

  .footer-content {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .footer-section {
    margin-bottom: 10px;
  }
}

@media (min-width: 768px) and (max-width: 1024px) {
  .header {
    padding: 10px 15px;
  }

  .title {
    font-size: 22px;
    margin-bottom:10px;
  }

  .search-container {
    width: 250px;
  }

  .content {
    padding-top: 120px;
  }

  .str {
    padding: 25px;
    font-size: 18px;
  }

  .text-with-image {
    gap: 50px;
  }

  .side-image {
    width: 300px;
  }

  .modal {
    max-width: 500px;
  }

  .subject-image {
    width: 120px;
  }

  .footer-content {
    flex-direction: row;
    justify-content: space-around;
  }
}

@media (min-width: 1024px) {
  .header {
    padding: 10px 30px;
  }

  .title {
    font-size: 28px;
  }

  .search-container {
    width: 350px;
  }

  .content {
    padding-top: 100px;
  }

  .str {
    padding: 30px;
    font-size: 20px;
  }

  .text-with-image {
    gap: 100px;
  }

  .side-image {
    width: 400px;
  }

  .modal {
    max-width: 600px;
  }

  .subject-image {
    width: 150px;
  }

  .footer-content {
    justify-content: space-between;
  }
}

@media (max-width: 480px) {
  .header {
    padding: 5px;
  }
  .about-heading {
    font-size: 25px;
  }
  .logo {
    width: 40px;
    display: none;
  }

  .title {
    font-size: 20px;
    margin-bottom:10px;
  }

  .search-container {
    width: 100%;
  }

  .search-input {
    font-size: 14px;
  }

  .content {
    padding-top: 130px;
  }

  .str {
    padding: 15px;
    font-size: 14px;
    margin-top:-10%;
  }

  .side-image {
    width: 100%;
    max-width: 250px;
  }

  .modal {
    padding: 10px;
  }

  .modal h2 {
    font-size: 20px;
  }

  .modal p {
    font-size: 14px;
  }

  .doc-link {
    padding: 8px 16px;
    font-size: 14px;
  }

  .footer {
    padding: 5px 10px;
  }

  .footer-heading {
    font-size: 14px;
  }

  .contact-link,
  .metelykx-link {
    font-size: 14px;
  }
}
/* Планшеты в альбомной ориентации */
@media (min-width: 768px) and (max-width: 1024px) and (orientation: landscape) {
  .header {
    padding: 10px 30px;
  }

  .str {
    max-width: 90%;
    padding: 25px;
    margin: 30px auto;
    width:950px;
  }

  .text-with-image {
    gap: 50px;
    align-items: center;
  }

  .text {
    min-width: unset;
    max-width: 55%;
    font-size: 18px;
  }

  .side-image {
    width: 40%;
    max-width: 350px;
  }

  .modal {
    max-width: 70%;
  }
}

/* Планшеты в портретной ориентации */
@media (min-width: 768px) and (max-width: 1024px) and (orientation: portrait) {
  .str {
    max-width: 95%;
    padding: 25px;
    width: 950px;
  }

  .text-with-image {
    flex-direction: column;
    gap: 40px;
  }

  .text {
    max-width: 100%;
    min-width: unset;
    font-size: 18px;
    padding: 0 20px;
  }

  .side-image {
    width: 60%;
    max-width: 400px;
    order: -1;
  }

  .modal {
    max-width: 80%;
    padding: 25px;
  }

  .modal-content {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .subject-image {
    width: 200px;
    margin-bottom: 20px;
  }
}

/* Общие стили для всех планшетов */
@media (min-width: 768px) and (max-width: 1024px) {
  

  .logo {
    width: 45px;
  }

  .title {
    font-size: 24px;
  }

  .search-container {
    width: 280px;
  }

  .footer-content {
    max-width: 90%;
    flex-wrap: wrap;
  }

  .footer-section {
    flex: 1 1 45%;
    margin-bottom: 15px;
  }

  .doc-link {
    font-size: 15px;
    padding: 12px 25px;
  }
}

/* Оптимизация для компактных планшетов */
@media (min-width: 768px) and (max-width: 900px) {
  .text {
    font-size: 17px;
  }

  .side-image {
    width: 45%;
  }

  .modal {
    max-width: 85%;
  }
}

</style>