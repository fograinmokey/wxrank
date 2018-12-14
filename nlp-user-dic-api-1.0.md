+ 2018年12月12日
    + 用户词典展示 
+ Data
    + NlpDicSearch 热词表
        + id (Long) - ID
        + word (String) - 热门词汇
        + searchNum (String) - 搜索次数
        + created (date) - 创建时间
        + modified (date) - 修改时间    
    + NlpDicSearchLog 热词日志表
        + id (Long) - ID
        + dateNode (Integer) - 日期
        + searchId (Long) - 用户搜索词ID
        + ssid (String) -  会话标识
        + number (Integer) - 计数标识
        + creator (Long) - 创建人
        + modifier (Long) - 修改人
        + created (date) - 创建时间
        + modified (date) - 修改时间
    + NlpDicDetialLog 词条详细日志表
        + id (Long) - ID
        + dateNode (Integer) - 日期
        + dicId (Long) - 词条ID
        + ssid (String) -  会话标识
        + categoryId (Long) - 分类ID 
        + number (Integer) - 计数标识
        + creator (Long) - 创建人
        + modifier (Long) - 修改人
        + created (date) - 创建时间
        + modified (date) - 修改时间

### 联想词条列表 [GET] /nlpUserDic/show?filter[word]=searchWord
+ Parameters
     + filter[word] = searchWord （搜索词）
     + categoryId 分类ID
     + categories 分类
+ Request (application/json)
    
      {
        "data": [
            {
                "id": 8213,
                "categoryId": 1,
                "word": "高频"
            },
            {
                "id": 13329,
                "categoryId": 3,
                "word": "高照光电"
            },
            {
                "id": 14048,
                "categoryId": 3,
                "word": "高频",
                "categories": [
                    {
                        "id": 1,
                        "title": "哈哈哈"
                    },
                    {
                        "id": 3,
                        "title": "厂家词典"
                    }
                ]
            },
            {
                "id": 13264,
                "categoryId": 3,
                "word": "高保真音响杂志"
            }
        ]
      }



### 热门词汇列表 [GET] /nlpDicSearchLog
+ Parameters
     + searchId 热词ID 
     + searchWord 热词
     + id 热词日志ID 
     

+ Request (application/json)

      {
        "data": [
            {
                "id": 5,
                "searchId": 11,
                "searchWord": "三星"
            },
            {
                "id": 1,
                "searchId": 23,
                "searchWord": "传媒大学"
            },
            {
                "id": 11,
                "searchId": 27,
                "searchWord": "A"
            },
            {
                "id": 3,
                "searchId": 24,
                "searchWord": "海子"
            },
            {
                "id": 2,
                "searchId": 15,
                "searchWord": "星"
            },
            {
                "id": 12,
                "searchId": 28,
                "searchWord": "B"
            },
            {
                "id": 4,
                "searchId": 25,
                "searchWord": "微信"
            }
        ]
    }

### (分类)高频词条榜单列表 [GET] /nlpDicDetialLog/dicRank
+ Parameters
     + filter[categoryId] = id 词典分类id
     + id 高频词条日志ID 
     + dicId 词条ID
     + categoryId 词条分类ID
     + categoryTitle 词条分类名称
     + word 词条
     + description 词条描述
+ Request (application/json)

      {
        "data": [
            {
                "id": 9,
                "dicId": 4,
                "categoryId": 3,
                "categoryTitle": "厂家词典",
                "word": "12-bar Blues",
                "description": "\n                    <p>This is the most common form of the blues, so named because it refers to the number of <a href=\"/insync/measure/\" title=\"measures\">measures</a> (12) or musical <a href=\"/insync/bar/\" title=\"bars\">bars</a> used to express the theme of the “typical” blues song, usually in 4/4 time. The 12-bar blues form is a <a href=\"/insync/progression-chord/\" title=\"progression\">progression</a> that’s divided into three four-bar segments and typically features three <a href=\"/insync/chord/\" title=\"chords\">chords</a> based upon the first, fourth and fifth notes of an 8-note <a href=\"/insync/scale/\" title=\"scale\">scale</a>.</p>\n                "
            },
            {
                "id": 1,
                "dicId": 1,
                "categoryId": 1,
                "categoryTitle": "哈哈哈",
                "word": "1-bit",
                "description": "\n                    <p>A phrase often used to characterize the operation of modern <a href=\"/insync/d-converter-adc/\" title=\"A/D\">A/D</a> and <a href=\"/insync/d-converter-dac/\" title=\"D/A\">D/A</a> <a href=\"/insync/converter/\" title=\"converters\">converters</a>. In the old days of <a href=\"/insync/digital/\" title=\"digital\">digital</a> <a href=\"/insync/audio/\" title=\"audio\">audio</a>, a multi-<a href=\"/insync/bit/\" title=\"bit\">bit</a> <a href=\"/insync/word/\" title=\"word\">word</a> was derived from each <a href=\"/insync/sample/\" title=\"sample\">sample</a> taken. Later, as technology progressed, designers began to employ what’s known as Delta Sigma Modulation to create a stream of pulses at a very fast rate. Each pulse provides only one bit of <a href=\"/insync/data/\" title=\"data\">data</a> (a zero or one), but at a high enough speed these pulses accurately (enough) capture an audio <a href=\"/insync/waveform/\" title=\"waveform\">waveform</a> for the purposes of digital recording (there are other applications too).</p>\n<p>This idea is based in part on the fact that <a href=\"/insync/quantization-noise/\" title=\"quantization distortion/noise\">quantization distortion/noise</a> is at its worst at the <a href=\"/insync/nyquist-frequency/\" title=\"Nyquist frequency\">Nyquist frequency</a>. At each <a href=\"/insync/octave/\" title=\"octave\">octave</a> below that the <a href=\"/insync/noise/\" title=\"noise\">noise</a> is reduced by 3<a href=\"/insync/db/\" title=\"dB\">dB</a>. So if your <a href=\"/insync/sample-rate/\" title=\"sampling rate\">sampling rate</a> is high enough you can actually use only one bit to represent the audio with enough <a href=\"/insync/dynamic-range/\" title=\"dynamic range\">dynamic range</a> to satisfy the human auditory system. This alone would require a very high sampling rate so in practice there are other technologies employed, such as <a href=\"/insync/noise-shaping/\" title=\"noise shaping\">noise shaping</a>, to fully accomplish the goal.</p>\n<p>In layman’s terms you can think of it in the following way: Each pulse merely tells you whether the waveform is headed up or down. Digital ones indicate the <a href=\"/insync/voltage/\" title=\"voltage\">voltage</a> is increasing, and digital zeros mean it is decreasing. Alternating ones and zeros mean it is staying the same. Put enough of those together and a picture of the audio waveform emerges.</p>\n "
            },
            {
                "id": 8,
                "dicId": 3,
                "categoryId": 3,
                "categoryTitle": "厂家词典",
                "word": "1/8 Space",
                "description": "\n                    <p>When a speaker or sound source is placed in a corner so it is near three surfaces (like the junction of two walls and the floor) it is said to be in 1/8th space. This is similar in concept to <a href=\"/insync/half-space/\">half space</a> (up against one wall) and <a href=\"/insync/quarter-space/\">quarter space</a> (at a junction between two walls). When sound sources are placed near surfaces in this way more of the energy gets forward into the listening space (see WFTD Half Space for more info). Putting a source into 1/8th space yields and increase of approximately 3 <a href=\"/insync/db/\">dB</a> more sound power level than quarter space, and 6 dB more than half space.</p>\n                "
            },
            {
                "id": 6,
                "dicId": 5,
                "categoryId": 2,
                "categoryTitle": "设备词典",
                "word": "12AX7",
                "description": "\n                    <p>The 12AX7 <a href=\"/insync/tube/\" title=\"tube\">tube</a> (also known as the ECC83 in the UK) is the quintessential modern guitar amplification preamp <a href=\"/insync/vacuum-tube/\" title=\"vacuum tube\">vacuum tube</a>. The 12AX7 is a twin-triode tube, meaning that it has two distinct <a href=\"/insync/triode/\" title=\"triodes\">triodes</a> inside one glass housing. These tubes are known for their high-gain sound, and often multiple 12AX7 tubes are cascaded to build up more and more gain. Generally, clean amps and clean channels of multi-channel amps have fewer 12AX7 tubes than the high-gain <a href=\"/insync/channel/\" title=\"channels\">channels</a> (and <a href=\"/insync/amplifier-instrument/\" title=\"amps\">amps</a>) do.</p>\n                "
            },
            {
                "id": 11,
                "dicId": 9,
                "categoryId": 5,
                "categoryTitle": "乐器词典",
                "word": "1394b",
                "description": "\n                    <p>Short for <a href=\"/insync/ieee-1394b-2002/\" title=\"IEEE 1394b-2002\">IEEE 1394b-2002</a>; the <a href=\"/insync/ieee/\" title=\"IEEE\">IEEE</a> spec describing <a href=\"/insync/firewire-800/\" title=\"Firewire 800\">Firewire 800</a>, with speeds up to 800<a href=\"/insync/mbps/\" title=\"Mbps\">Mbps</a> and interfacing using a 9-pin connector.</p>\n                "
            },
            {
                "id": 3,
                "dicId": 2,
                "categoryId": 1,
                "categoryTitle": "哈哈哈",
                "word": "1/4 Wave",
                "description": "\n                    <p>Refers to <a href=\"/insync/wavelength/\" title=\"wavelengths\">wavelengths</a> of audio or electromagnetic radiation (i.e. radio waves). One quarter of a wave denotes some dimension having a relationship with a signal such that it is 25% (or 1/4) as large as the space required for the entire wave of the signal. For example, in an RF (Radio <a href=\"/insync/frequency/\" title=\"Frequency\">Frequency</a>) or <a href=\"/insync/wireless/\" title=\"wireless\">wireless</a> system 1/4 wave antennas are common. A 1/4 wave (typically pronounced “Quarter Wave”) antenna’s length is 1/4 as long as the wavelength of the <a href=\"/insync/carrier/\" title=\"carrier\">carrier</a> frequency used by the system. There are also 1/2 wave antennas, and so on. Similar relationships exist in the field of acoustics (see WFTD <a href=\"/insync/quarter-space/\" title=\"Quarter Space\">Quarter Space</a>), though they aren’t usually this specific (audio systems generally have to respond to a wide range of frequencies) and it’s not as common to hear things referred to in this manner.</p>\n                "
            },
            {
                "id": 5,
                "dicId": 8,
                "categoryId": 3,
                "categoryTitle": "厂家词典",
                "word": "1394a",
                "description": "\n                    <p>Short for <a href=\"/insync/ieee-1394a-2000/\" title=\"IEEE 1394a-2000\">IEEE 1394a-2000</a>; the updated <a href=\"/insync/ieee/\" title=\"IEEE\">IEEE</a> spec describing <a href=\"/insync/firewire-400/\" title=\"Firewire 400\">Firewire 400</a>, with speeds up to 400<a href=\"/insync/mbps/\" title=\"Mbps\">Mbps</a> and interfacing using a 6-pin connector, with the addition of several enhancements over the original <a href=\"/insync/1394-2/\" title=\"1394\">1394</a> spec.</p>\n                "
            },
            {
                "id": 10,
                "dicId": 6,
                "categoryId": 5,
                "categoryTitle": "乐器词典",
                "word": "1-bit",
                "description": "\n                    <p>A type of connection found on <a href=\"/insync/guitar/\" title=\"guitars\">guitars</a> equipped with <a href=\"/insync/hexaphonic-pickup/\" title=\"hexaphonic\">hexaphonic</a> or “divided” <a href=\"/insync/pickup/\" title=\"pickup\">pickup</a> systems, specifically, those compatible with Roland equipment. The 13-pin output of the guitar can be connected to a guitar-to-<a href=\"/insync/midi/\" title=\"MIDI\">MIDI</a> converter, a guitar <a href=\"/insync/synthesizer/\" title=\"synthesizer\">synthesizer</a>, or a guitar <a href=\"/insync/modeling/\" title=\"modeling\">modeling</a> system. The 13-pin connector carries individual output from each of the six strings/hex pickup, and the <a href=\"/insync/signal/\" title=\"signal\">signal</a> from the guitar’s regular pickups as well as several control signals and <a href=\"/insync/phantom-power/\" title=\"\" phantom\"=\"\" power\"=\"\">“phantom” power</a> (assuming the connected device can provide phantom power). Note that the 13-pin connection itself does not carry MIDI information. An ancillary box must be used to convert the analog signals created by the hex pickup into MIDI note and control data.</p>\n<p>The pin-out for the connector is:</p>\n<p>Pin 1 – signal 1<br>\nPin 2 – signal 2<br>\nPin 3 – signal 3<br>\nPin 4 – signal 4<br>\nPin 5 – signal 5<br>\nPin 6 – signal 6<br>\nPin 7 – output from regular guitar pickups<br>\nPin 8 – synthesizer <a href=\"/insync/volume/\" title=\"volume\">volume</a> control signal<br>\nPin 9 – not used/no connection<br>\nPin 10 – synthesizer switch control signal (normally used for <a href=\"/insync/preset/\" title=\"preset\">preset</a> down)<br>\nPin 11 – synthesizer switch control signal (normally used for preset up)<br>\nPin 12 – +7 <a href=\"/insync/volt/\" title=\"volts\">volts</a> <a href=\"/insync/power-2/\" title=\"power\">power</a><br>\nPin 13 – -7 volts power<br>\n<a href=\"/insync/shield/\" title=\"Shield\">Shield</a> – <a href=\"/insync/ground/\" title=\"ground\">ground</a></p>\n                "
            },
            {
                "id": 4,
                "dicId": 10,
                "categoryId": 2,
                "categoryTitle": "设备词典",
                "word": "16-bit",
                "description": "\n                    <p>In <a href=\"/insync/digital/\" title=\"digital\">digital</a> <a href=\"/insync/data/\" title=\"data\">data</a> architecture, “16-bit” refers to the number of <a href=\"/insync/bit/\" title=\"bits\">bits</a> of the integers, memory addresses, and other data units used by the data in question. 16-bit architecture is significant in the <a href=\"/insync/audio/\" title=\"audio\">audio</a> world because <a href=\"/insync/compact-disc/\" title=\"compact disc \">compact disc </a> format is uses 16-bits of <a href=\"/insync/fixed-point/\" title=\"fixed point\">fixed point</a> integer data to represent a <a href=\"/insync/stereo/\" title=\"stereo\">stereo</a> audio <a href=\"/insync/file/\" title=\"file\">file</a>. For a long time, this was the most common <a href=\"/insync/bit-depth/\" title=\"bit depth\">bit depth</a> in the <a href=\"/insync/digital/\" title=\"digital\">digital</a> audio world — <a href=\"/insync/audio-interface/\" title=\"audio interfaces\">audio interfaces</a> would use 16-bit <a href=\"/insync/d-converter-adc/\" title=\"AD\">AD</a>/<a href=\"/insync/d-converter-dac/\" title=\"DA\">DA</a> <a href=\"/insync/converter/\" title=\"converters\">converters</a>, and early digital audio <a href=\"/insync/application-program/\" title=\"applications\">applications</a> natively supported only 16-bit audio. Later, 24-bit and now 32-bit floating point have become standards for digital audio processing, even when the final <a href=\"/insync/output/\" title=\"output\">output</a> data is 16-bit.  </p>\n                "
            },
            {
                "id": 7,
                "dicId": 7,
                "categoryId": 1,
                "categoryTitle": "哈哈哈",
                "word": "1394",
                "description": "\n                    <p>Short for <a href=\"/insync/ieee-1394-1995/\" title=\"IEEE 1394-1995\">IEEE 1394-1995</a>; the original <a href=\"/insync/ieee/\" title=\"IEEE\">IEEE</a> spec describing <a href=\"/insync/firewire-400/\" title=\"Firewire 400\">Firewire 400</a>, with speeds up to 400<a href=\"/insync/mbps/\" title=\"Mbps\">Mbps</a> and interfacing using a 6-pin connector.</p>\n                "
            }
        ]
      }
    
### 增加用户搜索词 [POST] /nlpDicSearch
+ Parameters
    +  word 用户在搜索框中要输入的词条，搜索的同时进行保存
+ Request (application/json)
    
      {
        "data":{
  	    "word":"大海"
        } 
      }

+ Response (application/json)
    
      {
        "data": 200
      }

