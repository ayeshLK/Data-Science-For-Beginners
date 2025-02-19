# सार्थक विज़ुअलाइज़ेशन बनाना

|![ सकेटच्नोते करने वाला [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/13-MeaningfulViz.png)|
|:---:|
| सार्थक विज़ुअलाइज़ेशन - _सकेटच्नोते करने वाला [@nitya](https://twitter.com/nitya)_ |

> "यदि आप डेटा को काफी देर तक प्रताड़ित करते हैं, तो यह कुछ भी कबूल कर लेगा" - [रोनाल्ड कोसे](https://en.wikiquote.org/wiki/Ronald_Coase)

एक डेटा वैज्ञानिक के बुनियादी कौशल में से एक सार्थक डेटा विज़ुअलाइज़ेशन बनाने की क्षमता है जो आपके सवालों के जवाब देने में मदद करता है। अपने डेटा की कल्पना करने से पहले, आपको यह सुनिश्चित करने की आवश्यकता है कि इसे साफ और तैयार किया गया है, जैसा कि आपने पिछले पाठों में किया था। उसके बाद, आप यह तय करना शुरू कर सकते हैं कि डेटा को सर्वोत्तम तरीके से कैसे प्रस्तुत किया जाए।

इस पाठ में, आप समीक्षा करेंगे:

1. सही चार्ट प्रकार कैसे चुनें
2. भ्रामक चार्टिंग से कैसे बचें
3. रंग के साथ कैसे काम करें
4. पठनीयता के लिए अपने चार्ट को कैसे स्टाइल करें
5. एनिमेटेड या 3डी चार्टिंग समाधान कैसे तैयार करें
6. क्रिएटिव विज़ुअलाइज़ेशन कैसे बनाएं

## [व्याख्यान पूर्व प्रश्नोत्तरी](https://witty-beach-04b13e603.1.azurestaticapps.net/quiz/24)

## सही चार्ट प्रकार चुनें

पिछले पाठों में, आपने चार्टिंग के लिए Matplotlib और Seaborn का उपयोग करके सभी प्रकार के दिलचस्प डेटा विज़ुअलाइज़ेशन बनाने का प्रयोग किया था। सामान्य तौर पर, आप इस तालिका का उपयोग करके पूछे जाने वाले प्रश्न के लिए [सही प्रकार का चार्ट](https://chartio.com/learn/charts/how-to-select-a-data-vizualization/) चुन सकते हैं:


| आपको चाहिए: | आपको उपयोग करना चाहिए: |
| -------------------------- | ----------------------------- |
| समय के साथ डेटा रुझान दिखाएं | रेखा |
| श्रेणियों की तुलना करें | बार, पाई |
| योग की तुलना करें | पाई, स्टैक्ड बार |
| रिश्ते दिखाएँ | तितर बितर, रेखा, पहलू, दोहरी रेखा |
| वितरण दिखाएं | तितर बितर, हिस्टोग्राम, बॉक्स |
| अनुपात दिखाएँ | पाई, डोनट, वफ़ल |

> ✅ आपके डेटा की बनावट के आधार पर, आपको इसका समर्थन करने के लिए दिए गए चार्ट को प्राप्त करने के लिए इसे टेक्स्ट से न्यूमेरिक में बदलने की आवश्यकता हो सकती है।

## धोखे से बचें

यहां तक ​​कि अगर एक डेटा वैज्ञानिक सही डेटा के लिए सही चार्ट चुनने के लिए सावधान है, तो ऐसे कई तरीके हैं जिनसे डेटा को एक बिंदु साबित करने के लिए प्रदर्शित किया जा सकता है, अक्सर डेटा को कम करने की कीमत पर। भ्रामक चार्ट और इन्फोग्राफिक्स के कई उदाहरण हैं!

[![हाउ चार्ट्स लाइ बाय अल्बर्टो काहिरा](./images/tornado.png)](https://www.youtube.com/watch?v=oX74Nge8Wkw "How चार्ट्स झूठ")

> भ्रामक चार्ट के बारे में एक सम्मेलन वार्ता के लिए ऊपर की छवि पर क्लिक करें

यह चार्ट दिनांक के आधार पर सत्य के विपरीत दिखाने के लिए X अक्ष को उलट देता है:

![खराब चार्ट 1](images/bad-chart-1.png)

[यह चार्ट](https://media.firstcoastnews.com/assets/WTLV/images/170ae16f-4643-438f-b689-50d66ca6a8d8/170ae16f-4643-438f-b689-50d66ca6a8d8_1140x641.jpg) और भी भ्रामक है, क्योंकि यह निष्कर्ष निकालने के लिए सही है कि, समय के साथ, विभिन्न काउंटियों में COVID मामलों में गिरावट आई है। वास्तव में, यदि आप तिथियों को करीब से देखते हैं, तो आप पाते हैं कि उन्हें उस भ्रामक गिरावट की प्रवृत्ति देने के लिए पुनर्व्यवस्थित किया गया है।

![खराब चार्ट 2](images/bad-chart-2.jpg)

यह कुख्यात उदाहरण धोखा देने के लिए रंग और एक फ़्लिप वाई अक्ष का उपयोग करता है: यह निष्कर्ष निकालने के बजाय कि बंदूक के अनुकूल कानून के पारित होने के बाद बंदूक की मौत बढ़ गई, वास्तव में आंख को यह सोचने के लिए मूर्ख बनाया जाता है कि विपरीत सच है:

![खराब चार्ट 3](images/bad-chart-3.jpg)

यह अजीब चार्ट दिखाता है कि कैसे अनुपात में हेरफेर किया जा सकता है, उल्लसित प्रभाव के लिए:

![खराब चार्ट 4](images/bad-chart-4.jpg)

अतुलनीय की तुलना करना अभी तक एक और छायादार चाल है। एक [अद्भुत वेब साइट](https://tylervigen.com/spurious-correlations) सभी 'नकली सहसंबंध' के बारे में है जो मेन में तलाक की दर और मार्जरीन की खपत जैसी 'तथ्यों' से संबंधित चीजों को प्रदर्शित करती है। एक Reddit समूह डेटा का [बदसूरत उपयोग](https://www.reddit.com/r/dataisugly/top/?t=all) भी एकत्र करता है।

यह समझना महत्वपूर्ण है कि भ्रामक चार्ट द्वारा आंख को कितनी आसानी से मूर्ख बनाया जा सकता है। भले ही डेटा वैज्ञानिक की मंशा अच्छी हो, लेकिन खराब प्रकार के चार्ट का चुनाव, जैसे कि बहुत अधिक श्रेणियां दिखाने वाला पाई चार्ट, भ्रामक हो सकता है।

## रंग

आपने ऊपर 'फ्लोरिडा गन हिंसा' चार्ट में देखा कि कैसे रंग चार्ट को अर्थ की एक अतिरिक्त परत प्रदान कर सकते हैं, विशेष रूप से वे जो मैटप्लोटलिब और सीबॉर्न जैसे पुस्तकालयों का उपयोग करके डिज़ाइन नहीं किए गए हैं जो विभिन्न सत्यापित रंग पुस्तकालयों और पट्टियों के साथ आते हैं। अगर आप हाथ से चार्ट बना रहे हैं, तो [रंग सिद्धांत](https://colormatters.com/color-and-design/basic-color-theory) का थोड़ा अध्ययन करें

> ✅ चार्ट डिजाइन करते समय सावधान रहें, कि एक्सेसिबिलिटी विज़ुअलाइज़ेशन का एक महत्वपूर्ण पहलू है। आपके कुछ उपयोगकर्ता कलर ब्लाइंड हो सकते हैं - क्या आपका चार्ट दृष्टिबाधित उपयोगकर्ताओं के लिए अच्छा प्रदर्शन करता है?

अपने चार्ट के लिए रंग चुनते समय सावधान रहें, क्योंकि रंग वह अर्थ बता सकता है जिसका आप इरादा नहीं कर सकते। ऊपर 'ऊंचाई' चार्ट में 'गुलाबी महिलाएं' एक विशिष्ट 'स्त्री' अर्थ व्यक्त करती हैं जो चार्ट की विचित्रता को जोड़ती है।

जबकि [रंग अर्थ](https://colormatters.com/color-symbolism/the-meanings-of-colors) दुनिया के अलग-अलग हिस्सों में अलग-अलग हो सकते हैं, और उनकी छाया के अनुसार अर्थ में परिवर्तन होता है। सामान्यतया, रंग अर्थों में शामिल हैं:

| रंग | अर्थ |
| ------ | ------------------- |
| लाल | शक्ति |
| नीला | भरोसा, वफादारी |
| पीला | खुशी, सावधानी |
| हरा | पारिस्थितिकी, भाग्य, ईर्ष्या |
| बैंगनी | खुशी |
| नारंगी | कंपन |

यदि आपको कस्टम रंगों के साथ चार्ट बनाने का काम सौंपा गया है, तो सुनिश्चित करें कि आपके चार्ट दोनों पहुंच योग्य हैं और आपके द्वारा चुना गया रंग उस अर्थ से मेल खाता है जिसे आप व्यक्त करने का प्रयास कर रहे हैं।

## पठनीयता के लिए अपने चार्ट को स्टाइल करना

यदि चार्ट पढ़ने योग्य नहीं हैं तो वे अर्थपूर्ण नहीं हैं! अपने डेटा के साथ अच्छी तरह से स्केल करने के लिए अपने चार्ट की चौड़ाई और ऊंचाई को स्टाइल करने पर विचार करने के लिए कुछ समय निकालें। यदि एक चर (जैसे सभी ५० राज्यों) को प्रदर्शित करने की आवश्यकता है, तो यदि संभव हो तो उन्हें Y अक्ष पर लंबवत रूप से दिखाएं ताकि क्षैतिज-स्क्रॉलिंग चार्ट से बचा जा सके।

अपनी कुल्हाड़ियों को लेबल करें, यदि आवश्यक हो तो एक किंवदंती प्रदान करें, और डेटा की बेहतर समझ के लिए टूलटिप्स प्रदान करें।

यदि आपका डेटा X अक्ष पर टेक्स्टुअल और वर्बोज़ है, तो आप बेहतर पठनीयता के लिए टेक्स्ट को एंगल कर सकते हैं। [Matplotlib](https://matplotlib.org/stable/tutorials/toolkits/mplot3d.html) ३डी प्लॉटिंग की पेशकश करता है, अगर आप डेटा इसका समर्थन करते हैं। परिष्कृत डेटा विज़ुअलाइज़ेशन `mpl_toolkits.mplot3d` का उपयोग करके तैयार किया जा सकता है।

![3d plots](images/3d.png)

## एनिमेशन और 3डी चार्ट डिस्प्ले

आज कुछ बेहतरीन डेटा विज़ुअलाइज़ेशन एनिमेटेड हैं। शर्ली वू ने डी3 के साथ अद्भुत काम किए हैं, जैसे '[फिल्म फूल](http://bl.ocks.org/sxywu/raw/d612c6c653fb8b4d7ff3d422be164a5d/)', जहां प्रत्येक फूल एक फिल्म का एक दृश्य है। गार्जियन के लिए एक और उदाहरण 'बस्स्ड आउट' है, ग्रीन्सॉक और डी3 के साथ विज़ुअलाइज़ेशन के संयोजन के साथ एक इंटरैक्टिव अनुभव और एक स्क्रॉलीटेलिंग आलेख प्रारूप यह दिखाने के लिए कि एनवाईसी लोगों को शहर से बाहर निकालकर अपनी बेघर समस्या को कैसे संभालता है।

![busing](images/busing.png)

> "बस्स्ड आउट: हाउ अमेरिका मूव्स इट्स बेघर" से [अभिभावक](https://www.theguardian.com/us-news/ng-interactive/2017/dec/20/bussed-out-america-moves-homeless-people-country-study). नादिह ब्रेमर और शर्ली वू द्वारा विज़ुअलाइज़ेशन

हालांकि यह पाठ इन शक्तिशाली विज़ुअलाइज़ेशन लाइब्रेरी को सिखाने के लिए पर्याप्त नहीं है, फिर भी एक एनिमेटेड सोशल नेटवर्क के रूप में "डेंजरस लाइजन्स" पुस्तक के विज़ुअलाइज़ेशन को प्रदर्शित करने के लिए लाइब्रेरी का उपयोग करके Vue.js ऐप में D3 पर अपना हाथ आज़माएं।

> "लेस लिआइसन्स डेंजरियस" एक पत्र-पत्रिका उपन्यास है, या पत्रों की एक श्रृंखला के रूप में प्रस्तुत उपन्यास है। 1782 में चोडरलोस डी लैक्लोस द्वारा लिखित, यह 18 वीं शताब्दी के अंत में फ्रांसीसी अभिजात वर्ग के दो द्वंद्वयुद्ध नायक, विकोमेट डी वालमोंट और मार्क्विस डी मेर्टुइल के शातिर, नैतिक रूप से दिवालिया सामाजिक युद्धाभ्यास की कहानी कहता है। दोनों अंत में अपने निधन से मिलते हैं लेकिन सामाजिक क्षति का एक बड़ा सौदा किए बिना नहीं। उपन्यास उनके मंडलियों में विभिन्न लोगों को लिखे गए पत्रों की एक श्रृंखला के रूप में सामने आता है, जो बदला लेने की साजिश रच रहा है या बस परेशानी पैदा कर रहा है। कथा के प्रमुख सरगनाओं को नेत्रहीन रूप से खोजने के लिए इन पत्रों का एक विज़ुअलाइज़ेशन बनाएं।

आप एक वेब ऐप पूरा करेंगे जो इस सोशल नेटवर्क का एक एनिमेटेड दृश्य प्रदर्शित करेगा। यह एक पुस्तकालय का उपयोग करता है जिसे Vue.js और D3 का उपयोग करके [एक नेटवर्क का दृश्य](https://github.com/emiliorizzo/vue-d3-network) बनाने के लिए बनाया गया था। जब ऐप चल रहा हो, तो आप डेटा को इधर-उधर करने के लिए स्क्रीन पर चारों ओर नोड्स खींच सकते हैं।
![liaisons](images/liaisons.png)

## प्रोजेक्ट: D3.js का उपयोग करके नेटवर्क दिखाने के लिए एक चार्ट बनाएं

> इस पाठ फ़ोल्डर में एक `solution` फ़ोल्डर शामिल है जहां आप अपने संदर्भ के लिए पूर्ण परियोजना ढूंढ सकते हैं।

1. स्टार्टर फोल्डर के रूट में README.md फाइल में दिए गए निर्देशों का पालन करें। सुनिश्चित करें कि आपके प्रोजेक्ट की निर्भरता स्थापित करने से पहले आपके मशीन पर NPM और Node.js चल रहे हैं।

2. `starter/src` फ़ोल्डर खोलें। आपको एक `assets` फ़ोल्डर मिलेगा जहां आप उपन्यास के सभी अक्षरों वाली एक .json फ़ाइल ढूंढ सकते हैं, जिसमें 'से' और 'प्रेषक' लिखावट हो।

3. विज़ुअलाइज़ेशन को सक्षम करने के लिए कोड को `components/Nodes.vue` में पूरा करें। `createLinks()` नामक विधि की तलाश करें और निम्नलिखित नेस्टेड लूप जोड़ें।

अक्षरों के लिए 'से' और 'से' डेटा कैप्चर करने के लिए .json ऑब्जेक्ट के माध्यम से लूप करें और `links` ऑब्जेक्ट का निर्माण करें ताकि विज़ुअलाइज़ेशन लाइब्रेरी इसका उपभोग कर सके:

```javascript
// अक्षरों के माध्यम से लूप
      let f = 0;
      let t = 0;
      for (var i = 0; i < letters.length; i++) {
          for (var j = 0; j < characters.length; j++) {
              
            if (characters[j] == letters[i].from) {
              f = j;
            }
            if (characters[j] == letters[i].to) {
              t = j;
            }
        }
        this.links.push({ sid: f, tid: t });
      }
  ```

टर्मिनल से अपना ऐप चलाएं (एनपीएम रन सर्व करें) और विज़ुअलाइज़ेशन का आनंद लें!

## चुनौती

भ्रामक विज़ुअलाइज़ेशन खोजने के लिए इंटरनेट का भ्रमण करें. लेखक उपयोगकर्ता को कैसे मूर्ख बनाता है, और क्या यह जानबूझकर किया गया है? विज़ुअलाइज़ेशन को यह दिखाने के लिए सही करने का प्रयास करें कि उन्हें कैसा दिखना चाहिए।

## [व्याख्यान के बाद प्रश्नोत्तरी](https://witty-beach-04b13e603.1.azurestaticapps.net/quiz/25)

## समीक्षा और आत्म अध्ययन

भ्रामक डेटा विज़ुअलाइज़ेशन के बारे में पढ़ने के लिए यहां कुछ लेख दिए गए हैं:

https://gizmodo.com/how-to-lie-with-data-visualization-1563576606

http://ixd.prattsi.org/2017/12/visual-lies-usability-in-deceptive-data-visualizations/

ऐतिहासिक संपत्तियों और कलाकृतियों के लिए इन रुचि विज़ुअलाइज़ेशन पर एक नज़र डालें:

https://handbook.pubpub.org/

इस लेख को देखें कि एनीमेशन आपके विज़ुअलाइज़ेशन को कैसे बढ़ा सकता है:

https://medium.com/@EvanSinar/use-animation-to-supercharge-data-visualization-cd905a882ad4

## कार्यभार

[अपना खुद का कस्टम विज़ुअलाइज़ेशन बनाएं](assignment.hi.md)
