# API Documentation

URL: `https://api.clearsky.services`

## Response Errors
- **400:** Bad Request
- **404:** Not Found
- **409:** Conflict
- **413** Payload Too Large
- **423:** Locked
- **500:** Internal Server Error
- **501:** Not Implemented
- **503:** Service Unavailable

## Rate Limiting

Anonymous endpoints:
- **Limits:** 5 requests per second

Authenticated endpoints:
- **Limits:** 30 requests per second

## Endpoints

### Anonymous:

#### 1.

- **Endpoint:** `/api/v1/anon/get-did/<handle>`
  - **Method:** `GET`
    - **Description:** Get the DID of a given handle
    - **Parameters:** handle
    - **Response:**
        ```json
            {
                "data":
                    {
                        "avatar_url":"https://cdn.bsky.app/img/avatar/plain/did:plc:w4xbfzo7kqfes5zb7r6qv3rw/bafkreicbh2mxpza6xhdwfwdvro33jlioue3g4elfp75u3je64dbvjk44la",
                        "did_identifier":"did:plc:w4xbfzo7kqfes5zb7r6qv3rw",
                        "identifier":"rudyfraser.com",
                        "pds": "https://shiitake.us-east.host.bsky.network",
                        "user_url":"https://bsky.app/profile/did:plc:w4xbfzo7kqfes5zb7r6qv3rw"
                    }
            }

#### 2.

- **Endpoint:** `/api/v1/anon/get-handle/<did>`
  - **Method:** `GET`
    - **Description:** Get the handle of a given DID
    - **Parameters:** DID
    - **Response:**
        ```json
            {
                "data":
                    {
                        "avatar_url":"https://cdn.bsky.app/img/avatar/plain/did:plc:w4xbfzo7kqfes5zb7r6qv3rw/bafkreicbh2mxpza6xhdwfwdvro33jlioue3g4elfp75u3je64dbvjk44la",
                        "handle_identifier":"rudyfraser.com",
                        "identifier":"did:plc:w4xbfzo7kqfes5zb7r6qv3rw",
                        "pds": "https://shiitake.us-east.host.bsky.network",
                        "user_url":"https://bsky.app/profile/did:plc:w4xbfzo7kqfes5zb7r6qv3rw"
                    }
            }

#### 3.

- **Endpoint:** `/api/v1/anon/total-users`
  - **Method:** `GET`
    - **Description:** Get user count information: total users, active users, deleted users
    - **Parameters:** none
      - **Response:**
          ```json
              { 
                  "as of":"2024-04-15T12:59:08.467076",
                      "data":
                          {
                              "active_count":
                                  {
                                      "displayname":"Active Users","value":"5,506,791"
                                  },
                              "deleted_count":
                                  {
                                      "displayname":"Deleted Users","value":"394,545"
                                  },
                              "total_count":
                                  {
                                      "displayname":"Total Users","value":"5,901,336"
                                  }
                          }
              }

#### 4.

- **Endpoint:** `/api/v1/anon/validation/validate-handle/<handle>`
  - **Method:** `GET`
    - **Description:** Validate a handle
    - **Parameters:** handle
    - **Response:**
        ```json
            {
                "data":
                    {
                        "valid":"true"
                    },
                "identity":"thieflord.dev"
            }
  
### 5.

- **Endpoint:** `/api/v1/anon/at-uri/<uri>`
  - **Method:** `GET`
    - **Description:** Get the URL of a given URI
    - **Parameters:** URI
    - **Response:**
        ```json
            {
                "data":
                {
                    "url": "https://bsky.app/profile/did:plc:bfjoqzne3tm5yxvpybdfahzo/lists/3jzmevbfqkj2u"
                }
            }

### 6.

- **Endpoint:** `/api/v1/anon/lists/fun-facts`
  - **Method:** `GET`
    - **Description:** Get top 20 blockers and blocked
    - **Parameters:** None
    - **Response:**
        ```json
            {
                "as of":"2024-04-15T12:59:08.467076",
                    "data":
                        {
                            "blocked":
                                [
                                    {"Handle":"jordanbpeterson.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:aeuetvb7vac3xay76nkphbks","block_count":19376,"did":"did:plc:aeuetvb7vac3xay76nkphbks"},
                                    {"Handle":"aifyco.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:s3kgjpyoec2fd7ztruqiaxwx","block_count":15526,"did":"did:plc:s3kgjpyoec2fd7ztruqiaxwx"},
                                    {"Handle":"shortcovid.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:rjlu6npi554qkz2jcvdt7mc3","block_count":13744,"did":"did:plc:rjlu6npi554qkz2jcvdt7mc3"},
                                    {"Handle":"endwokeness.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:byet53dwfmr5at7xk56zwmxv","block_count":13412,"did":"did:plc:byet53dwfmr5at7xk56zwmxv"},
                                    {"Handle":"mdbreathe.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:cmo3ypyyvybcgyi2tg2x4sge","block_count":10384,"did":"did:plc:cmo3ypyyvybcgyi2tg2x4sge"},
                                    {"Handle":"90sanime.pics","ProfileURL":"https://bsky.app/profile/did:plc:5krm4pb5gecb5uawvgr7uxuu","block_count":10194,"did":"did:plc:5krm4pb5gecb5uawvgr7uxuu"},
                                    {"Handle":"anonymous.expectus.fyi","ProfileURL":"https://bsky.app/profile/did:plc:xfqcsi7wuwedeqaa5m7aih44","block_count":9990,"did":"did:plc:xfqcsi7wuwedeqaa5m7aih44"},
                                    {"Handle":"pobachan.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:n6hm45eke7a5qtlqxosdlfus","block_count":9583,"did":"did:plc:n6hm45eke7a5qtlqxosdlfus"},
                                    {"Handle":"catswithaura.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:wwakmfq74pvducx2pbbdxhlg","block_count":9030,"did":"did:plc:wwakmfq74pvducx2pbbdxhlg"},
                                    {"Handle":"afdberlin.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:vzakzcxo3dqgjvlgmqlakcb5","block_count":8868,"did":"did:plc:vzakzcxo3dqgjvlgmqlakcb5"},
                                    {"Handle":"thedevil.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:k2weqoffrljoi7d45jjhjaqk","block_count":8726,"did":"did:plc:k2weqoffrljoi7d45jjhjaqk"},
                                    {"Handle":"9gag.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:56eikwlvdd4htq727624spkg","block_count":8444,"did":"did:plc:56eikwlvdd4htq727624spkg"},
                                    {"Handle":"nowbreezing.ntw.app","ProfileURL":"https://bsky.app/profile/did:plc:mcb6n67plnrlx4lg35natk2b","block_count":8267,"did":"did:plc:mcb6n67plnrlx4lg35natk2b"},
                                    {"Handle":"womensart1.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:jfpub26kfrtponcqzi7i7udl","block_count":7973,"did":"did:plc:jfpub26kfrtponcqzi7i7udl"},
                                    {"Handle":"ewerickson.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:2gwoe546lp565vxmzzy2emsl","block_count":7815,"did":"did:plc:2gwoe546lp565vxmzzy2emsl"},
                                    {"Handle":"artificial.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:gr3zsqab63cfvv7nao4mrh7v","block_count":7237,"did":"did:plc:gr3zsqab63cfvv7nao4mrh7v"},
                                    {"Handle":"poeticalphotos.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:ha5tvry6kkxiujam6kyjgagg","block_count":7171,"did":"did:plc:ha5tvry6kkxiujam6kyjgagg"},
                                    {"Handle":"usmc.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:gl5rxplcsmkdygh4w7jjjugd","block_count":6949,"did":"did:plc:gl5rxplcsmkdygh4w7jjjugd"},
                                    {"Handle":"julianreichelt.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:hwbjiajbxxij27fzdxwgp7h7","block_count":6905,"did":"did:plc:hwbjiajbxxij27fzdxwgp7h7"},
                                    {"Handle":"funnyordie.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:m4wkkbc4k5e46hus7zy3tijd","block_count":6767,"did":"did:plc:m4wkkbc4k5e46hus7zy3tijd"}
                                ],
                            "blocked_aid":
                                {
                                    "did:plc:2gwoe546lp565vxmzzy2emsl":"bafkreigkyri2ge24a2gjvbyfqhpv72ean3kqdr5im6e3njdgfcosgtaly4",
                                    "did:plc:56eikwlvdd4htq727624spkg":"bafkreic2xkbo646nxl44z3zk2zeighlvsgltoqjoolc3ihc26p4sdxityu",
                                    "did:plc:5krm4pb5gecb5uawvgr7uxuu":"bafkreie6vz5gykxxdf777yiirarw3eyvycbg46to6dknynbxwqrcsl5mfu",
                                    "did:plc:aeuetvb7vac3xay76nkphbks":"bafkreibnus2odyijekzkiarrthjwwjjaxbqor5ueopfsa3ezk3doyd3t2a",
                                    "did:plc:byet53dwfmr5at7xk56zwmxv":"bafkreie5wkm74v6kewoeukcla2hdvzfcfsmqvtm5mhnxdvabgjd2fc2jvm",
                                    "did:plc:cmo3ypyyvybcgyi2tg2x4sge":"bafkreicvorlfinnmygp5ibd65wjvr6tq526fkaksgsrls7v4bw3caluko4",
                                    "did:plc:gl5rxplcsmkdygh4w7jjjugd":"bafkreigen3wdgs3dyjdvryjrhsks26loqntomm3izgoxfppzk27h64hyta",
                                    "did:plc:gr3zsqab63cfvv7nao4mrh7v":"bafkreias26vb2aujzaktxnnzgkqkydf3unkdu4qd6l765fdvqbt5xe6hma",
                                    "did:plc:ha5tvry6kkxiujam6kyjgagg":"bafkreigdoleeclxuwukhhqwqsftrofuazhqhvab377v3tyk4jazkvn2ixi",
                                    "did:plc:hwbjiajbxxij27fzdxwgp7h7":"bafkreidsd5niiokjiqkrgi3ko444rne6t2qhaeyvyhvz7ahjgyyih3xzie",
                                    "did:plc:jfpub26kfrtponcqzi7i7udl":"bafkreib35vtob7wsqhye4t3tgkoprye5qeqv4fauedcqomfm3yj6oae52i",
                                    "did:plc:k2weqoffrljoi7d45jjhjaqk":"bafkreiamm5zsg4fs5gt3qv6ljam57a45ulb2ova5zk2f7sagr4cvowiroq",
                                    "did:plc:m4wkkbc4k5e46hus7zy3tijd":"bafkreibxjsxyd452tupsqjw252jjnsaqaooyqdhvrdafsu3rhprtcsktfi",
                                    "did:plc:mcb6n67plnrlx4lg35natk2b":"bafkreicnd6h4vh3fggtlvajlxizo2qxp5vc3pt7sbqasinlung2ibuwp5q",
                                    "did:plc:n6hm45eke7a5qtlqxosdlfus":"bafkreihpmne2lhgdeqpbu6yo4hbi64oghxc4yrglx37oc7qbmg43bl6lm4",
                                    "did:plc:rjlu6npi554qkz2jcvdt7mc3":"bafkreia7nn5zcs7eftzihvaqhcqd2wge2s4xyel2rebpvtk7p4sjwwae3y",
                                    "did:plc:s3kgjpyoec2fd7ztruqiaxwx":"",
                                    "did:plc:vzakzcxo3dqgjvlgmqlakcb5":"bafkreibcalpe4ceeh27wuu42irlkgb3rm6dcxyk3bqcfe7xnjpxxiqojsy",
                                    "did:plc:wwakmfq74pvducx2pbbdxhlg":"bafkreieeqwlz7l4lk6eztvyfnowockjstvksrqsfveb7hk2rv5rkfuihtm",
                                    "did:plc:xfqcsi7wuwedeqaa5m7aih44":"bafkreic6auduax3rkmtm6xgaetan5osdm454a4y5wc5ryfcjkg5gnfqhmu"},
                            "blockers":
                                [
                                    {"Handle":"jpegxl.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:pz7bbehnhhfl2y43kvgsc47j","block_count":324147,"did":"did:plc:pz7bbehnhhfl2y43kvgsc47j"},
                                    {"Handle":"tw1nk.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:2np6uovyvjnbgh4l4en5t44a","block_count":314940,"did":"did:plc:2np6uovyvjnbgh4l4en5t44a"},
                                    {"Handle":"chiefkeef.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:e4fsmjcj33khuqi6prspceiy","block_count":291146,"did":"did:plc:e4fsmjcj33khuqi6prspceiy"},
                                    {"Handle":"jessiealiceboy.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:kuzwlmess4wyoufryjgmub7e","block_count":182344,"did":"did:plc:kuzwlmess4wyoufryjgmub7e"},
                                    {"Handle":"evanforman.com","ProfileURL":"https://bsky.app/profile/did:plc:ph5wyq6qnpvjgzoxzilzxwn7","block_count":41169,"did":"did:plc:ph5wyq6qnpvjgzoxzilzxwn7"},
                                    {"Handle":"fresh-newlook.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:6odst3452scxthx7w3v2tiav","block_count":40324,"did":"did:plc:6odst3452scxthx7w3v2tiav"},
                                    {"Handle":"thewrittentevs.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:mauk6khnlclkr5k2hnezgmja","block_count":20378,"did":"did:plc:mauk6khnlclkr5k2hnezgmja"},
                                    {"Handle":"whydoilikethis.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:g2xshwj4o33b5wzxs3xspfxk","block_count":18774,"did":"did:plc:g2xshwj4o33b5wzxs3xspfxk"},
                                    {"Handle":"populuxe.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:cgxxlxuypmkdqdcpioqny5r6","block_count":17277,"did":"did:plc:cgxxlxuypmkdqdcpioqny5r6"},
                                    {"Handle":"kuriousgeorge.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:43palulr6mc63o4tt2xrpxum","block_count":16940,"did":"did:plc:43palulr6mc63o4tt2xrpxum"},
                                    {"Handle":"art-curator.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:25gjrl4ybzmdxxopfpk47mpy","block_count":15918,"did":"did:plc:25gjrl4ybzmdxxopfpk47mpy"},
                                    {"Handle":"lukatv.lol","ProfileURL":"https://bsky.app/profile/did:plc:xdvfcobxq6qs7y2dg4luxiga","block_count":15145,"did":"did:plc:xdvfcobxq6qs7y2dg4luxiga"},
                                    {"Handle":"hamandegger.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:wgiw4zvjhfhhubf6dtocjern","block_count":15117,"did":"did:plc:wgiw4zvjhfhhubf6dtocjern"},
                                    {"Handle":"jerrybuchko.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:m2sds432e3fp3xk2q5m2f344","block_count":14904,"did":"did:plc:m2sds432e3fp3xk2q5m2f344"},
                                    {"Handle":"likeamilkdud.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:d2c3m3xnz4e3x774bq7w43pc","block_count":14513,"did":"did:plc:d2c3m3xnz4e3x774bq7w43pc"},
                                    {"Handle":"sunsetsnow.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:axrs65zc6hj3m5axp3fth6pw","block_count":14350,"did":"did:plc:axrs65zc6hj3m5axp3fth6pw"},
                                    {"Handle":"eugeniemona.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:rb7uc26lx3kn6dl756grswrj","block_count":11045,"did":"did:plc:rb7uc26lx3kn6dl756grswrj"},
                                    {"Handle":"northrax.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:o6dfdlenwvg3rhvvi27ai7sq","block_count":10893,"did":"did:plc:o6dfdlenwvg3rhvvi27ai7sq"},
                                    {"Handle":"jrbolt.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:5dn6hroc3v7i53cz6hpq3zgv","block_count":10599,"did":"did:plc:5dn6hroc3v7i53cz6hpq3zgv"},
                                    {"Handle":"articulatemadness.com","ProfileURL":"https://bsky.app/profile/did:plc:if6lbbt7vjduzzfdlgea4m4n","block_count":10598,"did":"did:plc:if6lbbt7vjduzzfdlgea4m4n"}
                                ],
                            "blockers_aid":
                                {
                                    "did:plc:25gjrl4ybzmdxxopfpk47mpy":"",
                                    "did:plc:2np6uovyvjnbgh4l4en5t44a":"bafkreifrkgduawqxsgvtwdbxuiyf3an6csbafowd6m5lj2wprhlo3ytsom",
                                    "did:plc:43palulr6mc63o4tt2xrpxum":"bafkreib3oemett3th4df4joxyrztwi53yajqdfbqsgno5gqcgfucz4kamu",
                                    "did:plc:5dn6hroc3v7i53cz6hpq3zgv":"bafkreigiy7jwy7rywt2s7mid6vcksweekxbghk4hwn4kkdamtzyzwzvczi",
                                    "did:plc:6odst3452scxthx7w3v2tiav":"bafkreid4znwozgnn5vz7jhk5wsub73dkwnqf3hu4cs7u5njewqiixugi4q",
                                    "did:plc:axrs65zc6hj3m5axp3fth6pw":"bafkreicqwvuqqhzi6vzexyi7c5arfov4cqr26hkxggameqmd3nkldovud4",
                                    "did:plc:cgxxlxuypmkdqdcpioqny5r6":"bafkreiaaaksgtbfk7wvuwrzgyrssvfqm7gzxmilsf6w4jz33eiz6auwyo4",
                                    "did:plc:d2c3m3xnz4e3x774bq7w43pc":"bafkreig672aogrqgj6hj3fhilgetxrfty4pf3vv2q25sjzm4uicnvs3wru",
                                    "did:plc:e4fsmjcj33khuqi6prspceiy":"bafkreifykraakgmpblk7q574amv23yffetp43fmxubja4vnhu74rob3ida",
                                    "did:plc:g2xshwj4o33b5wzxs3xspfxk":"bafkreiabzguv3uvpth3a3w2fvgwhvl7qzmvcqn63sodk4ds5lp5v3g2y34",
                                    "did:plc:if6lbbt7vjduzzfdlgea4m4n":"bafkreidcngprpdc7qqp6f3dak4zjjjakekoaemnp6puyemofd2t4rr3uu4",
                                    "did:plc:kuzwlmess4wyoufryjgmub7e":"bafkreih5rrhkaafw57z6ovbktfjdgavmfjt7fvqdjblz444lr4gq3ozrxu",
                                    "did:plc:m2sds432e3fp3xk2q5m2f344":"bafkreifvyu5u5zmrr77nf6cpvapj6dfhbbo6ibfhvmmeccanwkghfdfu74",
                                    "did:plc:mauk6khnlclkr5k2hnezgmja":"bafkreigbmijkhof4qsutjttodry4h33euthlu6xcvezzxlie2aejuhteaq",
                                    "did:plc:o6dfdlenwvg3rhvvi27ai7sq":"bafkreig3gzi2uo26wwf6v52quhd6sci43bzjzkai2jnqzq7vty755dszle",
                                    "did:plc:ph5wyq6qnpvjgzoxzilzxwn7":"bafkreifif4aj4lovhiqkxnr5r6iceu4c5evijqqm45jsi5f2u5ajim2syq",
                                    "did:plc:pz7bbehnhhfl2y43kvgsc47j":"bafkreiaqgit3wn3rny4mpixcbwedj3v4k76nf6tbal77d5jrqr7vnd34ua",
                                    "did:plc:rb7uc26lx3kn6dl756grswrj":"bafkreigahnudz2pbcmymmei54wuomvxemn25ofzakjonjcmwaukdyf3hki",
                                    "did:plc:wgiw4zvjhfhhubf6dtocjern":"bafkreibkkfry5co2opt3itgcx3y2dkuqwpy3kzwkmf5b6b7q6i76qutduu",
                                    "did:plc:xdvfcobxq6qs7y2dg4luxiga":"bafkreif5mw66ul2xxt2wzlddvljcydfk4wwkpkyyddgucsd3r44vtpv6b4"
                                }
                        }
            }
      
### 7.

- **Endpoint:** `/api/v1/anon/lists/funer-facts`
  - **Method:** `GET`
    - **Description:** Get top 20 blockers and blocked in the last 24 hours
    - **Parameters:** None
    - **Response:**
        ```json
            {
                "as of":"2024-04-16T01:09:11.058137",
                    "data":
                        {
                            "blocked24":
                                [
                                    {"Handle":"iriepirate21.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:nwjrnf36guvfjfdehfj4kxcp","block_count":320,"did":"did:plc:nwjrnf36guvfjfdehfj4kxcp"},
                                    {"Handle":"kiffboet.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:cbfpkroum2sijzt2gtupmzvr","block_count":176,"did":"did:plc:cbfpkroum2sijzt2gtupmzvr"},
                                    {"Handle":"sb58.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:diplgox44wvs32m2c66uc6pd","block_count":118,"did":"did:plc:diplgox44wvs32m2c66uc6pd"},
                                    {"Handle":"catiadireita.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:p6wzx4xynvlqenobnkhv6uvo","block_count":117,"did":"did:plc:p6wzx4xynvlqenobnkhv6uvo"},
                                    {"Handle":"respost.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:thzbb5omc46drqaiqzxy7rqa","block_count":115,"did":"did:plc:thzbb5omc46drqaiqzxy7rqa"},
                                    {"Handle":"positional.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:xneejsru4m6dres5gr7v6xbg","block_count":112,"did":"did:plc:xneejsru4m6dres5gr7v6xbg"},
                                    {"Handle":"riajsolonarob.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:doixrg35vtfzhyke56qgvtxt","block_count":111,"did":"did:plc:doixrg35vtfzhyke56qgvtxt"},
                                    {"Handle":"direitasnake.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:vqhmn52bbkr2si2mposcay3i","block_count":106,"did":"did:plc:vqhmn52bbkr2si2mposcay3i"},
                                    {"Handle":"alfineteireal.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:x466nsmtdzmp37r5wphul2em","block_count":102,"did":"did:plc:x466nsmtdzmp37r5wphul2em"},
                                    {"Handle":"exbolsonaro.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:e3oym32eei3yhk6rmfuvao3v","block_count":100,"did":"did:plc:e3oym32eei3yhk6rmfuvao3v"},
                                    {"Handle":"kouroumatchingapp.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:xnwbw2t44oazdarjfrjp3kkk","block_count":97,"did":"did:plc:xnwbw2t44oazdarjfrjp3kkk"},
                                    {"Handle":"feet212.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:jgrzlsdahn7jbaswufqgkzxz","block_count":95,"did":"did:plc:jgrzlsdahn7jbaswufqgkzxz"},
                                    {"Handle":"olisvalsaraiva.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:ivy2kntgpptnknlrzblthbq2","block_count":93,"did":"did:plc:ivy2kntgpptnknlrzblthbq2"},
                                    {"Handle":"limpioplayas.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:zr4bhjq4grn2nqxy2k7n2ond","block_count":91,"did":"did:plc:zr4bhjq4grn2nqxy2k7n2ond"},
                                    {"Handle":"alexandrestf.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:2ceohhpudkp67sd7m53vgbru","block_count":89,"did":"did:plc:2ceohhpudkp67sd7m53vgbru"},
                                    {"Handle":"naikumaart.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:ka4cbx4qxi2csnfkhxnd4s4b","block_count":87,"did":"did:plc:ka4cbx4qxi2csnfkhxnd4s4b"},
                                    {"Handle":"peritodigital.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:zvkq5gpsa5egltscqmeorknf","block_count":82,"did":"did:plc:zvkq5gpsa5egltscqmeorknf"},
                                    {"Handle":"s9o.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:ybibukp72x2hj7a5ueav5wsl","block_count":82,"did":"did:plc:ybibukp72x2hj7a5ueav5wsl"},
                                    {"Handle":"koda0702.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:hoyor2vepcc572jhljn7aksl","block_count":81,"did":"did:plc:hoyor2vepcc572jhljn7aksl"},
                                    {"Handle":"luizfelipepa.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:qi5bn6a7by2eni2gr7r7icv2","block_count":80,"did":"did:plc:qi5bn6a7by2eni2gr7r7icv2"}
                                ],
                            "blocked_aid":
                                {
                                    "did:plc:2ceohhpudkp67sd7m53vgbru":"bafkreih3j7xwucs2mwcthndwk6zp7jgacigofiday4ce6oorwwlnxjnhw4",
                                    "did:plc:cbfpkroum2sijzt2gtupmzvr":"bafkreigywh27dc22yau3bhk23zutyqn7lj4wipnljjporynmbz5wt564fe",
                                    "did:plc:diplgox44wvs32m2c66uc6pd":"",
                                    "did:plc:doixrg35vtfzhyke56qgvtxt":"bafkreic5c7n3alh3fchmwuscsfbjrr74lgoef5fjnekykkn462q2rzrurm",
                                    "did:plc:e3oym32eei3yhk6rmfuvao3v":"bafkreia3hpgxdsxk2gx35udxeadafa6wohdgg4vqgagcwx2ubagms6srfu",
                                    "did:plc:hoyor2vepcc572jhljn7aksl":"",
                                    "did:plc:ivy2kntgpptnknlrzblthbq2":"",
                                    "did:plc:jgrzlsdahn7jbaswufqgkzxz":"bafkreihq26obkyo66pk5ekksgnp5r5uzilulxl6jv6o64aji6q372t4wsa",
                                    "did:plc:ka4cbx4qxi2csnfkhxnd4s4b":"bafkreicf66qjctadh5qwkqirbrtnyqr3rsvu4h5wzkjnahfuogxh5syo54",
                                    "did:plc:nwjrnf36guvfjfdehfj4kxcp":"bafkreigj4ee5sn2czey3rmnf6rhxknkna7555aar46pu7e2flgg5psrru4",
                                    "did:plc:p6wzx4xynvlqenobnkhv6uvo":"bafkreie7qm6ff4a5zohtb3b536x34smdvmqz2mxhpezvkjsg3t7raw462q",
                                    "did:plc:qi5bn6a7by2eni2gr7r7icv2":"bafkreigdol6ipw7hi3pt2fudlbo5fgy6vk3wm5n2pmxdypt5yp6yiu5mti",
                                    "did:plc:thzbb5omc46drqaiqzxy7rqa":"bafkreiesdvnrkgwyolreo4jwlp3l4ixd5tpzgft5ss6tgk4sstdflcgy6u",
                                    "did:plc:vqhmn52bbkr2si2mposcay3i":"bafkreie7sbzmvwtgmd5v76o6vy6kjeyeqafqllrgjimmtehdeuixo34sve",
                                    "did:plc:x466nsmtdzmp37r5wphul2em":"bafkreia44st4z5e7wwjoeww4glg4gbdo2tgqqwn52iejoytj7gck2g36ny",
                                    "did:plc:xneejsru4m6dres5gr7v6xbg":"",
                                    "did:plc:xnwbw2t44oazdarjfrjp3kkk":"bafkreibnfgzjz4nn23ents3krszjnelqsd7zdz2rswvqq274o5d6lxf7rq",
                                    "did:plc:ybibukp72x2hj7a5ueav5wsl":"bafkreic6z2qqglkyp4iefvj7lvjizhthfrqdkcskrrfd3sgvlnlitej7hu",
                                    "did:plc:zr4bhjq4grn2nqxy2k7n2ond":"bafkreiem5xwzlfnl2wlreabkedxo473k4wzwo3okctlvsm6ibvqn6mu4cy",
                                    "did:plc:zvkq5gpsa5egltscqmeorknf":""
                                },
                            "blockers24":
                                [
                                    {"Handle":"jimmygresik.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:wvgzdrosihvh23fw3s3vrc2t","block_count":396,"did":"did:plc:wvgzdrosihvh23fw3s3vrc2t"},
                                    {"Handle":"hamandegger.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:wgiw4zvjhfhhubf6dtocjern","block_count":385,"did":"did:plc:wgiw4zvjhfhhubf6dtocjern"},
                                    {"Handle":"fresh-newlook.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:6odst3452scxthx7w3v2tiav","block_count":258,"did":"did:plc:6odst3452scxthx7w3v2tiav"},
                                    {"Handle":"crabcakes455.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:keyxowxtn6f4excmztwdm7ty","block_count":255,"did":"did:plc:keyxowxtn6f4excmztwdm7ty"},
                                    {"Handle":"asaidperson.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:mbwsjp4q4ehbhgjf6xt4qaom","block_count":185,"did":"did:plc:mbwsjp4q4ehbhgjf6xt4qaom"},
                                    {"Handle":"nz1.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:n7cpgjpsbjkwu3kabh5o3xws","block_count":184,"did":"did:plc:n7cpgjpsbjkwu3kabh5o3xws"},
                                    {"Handle":"iran-rn.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:vkof2dfgcttmaslwzmv76fhx","block_count":170,"did":"did:plc:vkof2dfgcttmaslwzmv76fhx"},
                                    {"Handle":"manickian.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:sdzj2amytwzejj3i5ixvfikb","block_count":167,"did":"did:plc:sdzj2amytwzejj3i5ixvfikb"},
                                    {"Handle":"teapotgirl.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:wg5pgjo2xp5eymgu7guskxht","block_count":166,"did":"did:plc:wg5pgjo2xp5eymgu7guskxht"},
                                    {"Handle":"xrleavt.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:cdavaylpqcpa4nu6itqskcr6","block_count":166,"did":"did:plc:cdavaylpqcpa4nu6itqskcr6"},
                                    {"Handle":"claudia10.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:kjfzkvmygiz47sklzq4c373p","block_count":162,"did":"did:plc:kjfzkvmygiz47sklzq4c373p"},
                                    {"Handle":"chrisnasuecia.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:tb7h3hjsmk3mkpi2ey7p2no3","block_count":146,"did":"did:plc:tb7h3hjsmk3mkpi2ey7p2no3"},
                                    {"Handle":"isabelacastro.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:yjlryeay3f5owqqvnvtc4rjw","block_count":144,"did":"did:plc:yjlryeay3f5owqqvnvtc4rjw"},
                                    {"Handle":"kouorz.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:pkmw43mzucdrw5aqcqqmbgyr","block_count":133,"did":"did:plc:pkmw43mzucdrw5aqcqqmbgyr"},
                                    {"Handle":"marciamoura.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:72jvaviwihjxcqbbv2oxevu3","block_count":133,"did":"did:plc:72jvaviwihjxcqbbv2oxevu3"},
                                    {"Handle":"irapua.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:te3znuszc6vsv6t32eu6dhja","block_count":119,"did":"did:plc:te3znuszc6vsv6t32eu6dhja"},
                                    {"Handle":"sonjamaria.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:7bcengteojtq4b2uvtc5lqvu","block_count":118,"did":"did:plc:7bcengteojtq4b2uvtc5lqvu"},
                                    {"Handle":"jessi123.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:7hie2hsrf7sr34o6e7qnyub7","block_count":114,"did":"did:plc:7hie2hsrf7sr34o6e7qnyub7"},
                                    {"Handle":"spaced1999aka.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:qahup5ytjl76lzkbtwmj6ci4","block_count":111,"did":"did:plc:qahup5ytjl76lzkbtwmj6ci4"},
                                    {"Handle":"paulalight.bsky.social","ProfileURL":"https://bsky.app/profile/did:plc:24cnoogaatrubxvqkmoo6v27","block_count":111,"did":"did:plc:24cnoogaatrubxvqkmoo6v27"}
                                ],
                            "blockers_aid":
                                {
                                    "did:plc:24cnoogaatrubxvqkmoo6v27":"bafkreialxjrgorrr6io5s7nxxgmofupmbkokdw3dz2yrcjjbsjgs7he37u",
                                    "did:plc:6odst3452scxthx7w3v2tiav":"bafkreid4znwozgnn5vz7jhk5wsub73dkwnqf3hu4cs7u5njewqiixugi4q",
                                    "did:plc:72jvaviwihjxcqbbv2oxevu3":"bafkreic7o47efe64g37odwyvjm5qfgpw5b3vhfncuvcdnuxkeac7ewh4qq",
                                    "did:plc:7bcengteojtq4b2uvtc5lqvu":"bafkreickinjphkzwkhc4rzqs3lsuvvsdr4cpwdeht7meou7sy2lo2cl6am",
                                    "did:plc:7hie2hsrf7sr34o6e7qnyub7":"bafkreihvssk4fguxikzu54orthodm5ftuxgfv7wpbdyd62b5m3jdrozgdu",
                                    "did:plc:cdavaylpqcpa4nu6itqskcr6":"bafkreidznkiz6uiv53bfvpogmn7bgl2lzhw33gqh45vupvqughcfcarpai",
                                    "did:plc:keyxowxtn6f4excmztwdm7ty":"bafkreibixg7nw4feoz7jogrjkd33inbjvadk3wbxdjt3b36vhny74evilm",
                                    "did:plc:kjfzkvmygiz47sklzq4c373p":"bafkreicufkiisvbr5iub7rg6xrvbd6ho5fetdzw2om5i6qrqczkivnxijq",
                                    "did:plc:mbwsjp4q4ehbhgjf6xt4qaom":"bafkreiha2rexwqiygdbmxprhej36v3kefdww3y2caemdnc64iowr7m3cie",
                                    "did:plc:n7cpgjpsbjkwu3kabh5o3xws":"bafkreie4qhnpx4fdoekb2ymyvc76xp3mjqypbcyuqlpf44cyc2kmpml6ja",
                                    "did:plc:pkmw43mzucdrw5aqcqqmbgyr":"bafkreihypvodpnwccbqlxl4x6e5pw7tt5v3i3eb5bq5nyob4wbsusc3xki",
                                    "did:plc:qahup5ytjl76lzkbtwmj6ci4":"bafkreiarze5mvjidmk5kq6olkmfagtft2zpkkhfona55iubbf2jvosorai",
                                    "did:plc:sdzj2amytwzejj3i5ixvfikb":"bafkreifujrfrkg7sqh2f65gp2bcdqttbvynxjsv25trascq2lmfbbhk4ly",
                                    "did:plc:tb7h3hjsmk3mkpi2ey7p2no3":"bafkreie27wybrjexqqciddhbaen6h47ixgrp6325ezwbhclqszejf7s7xm",
                                    "did:plc:te3znuszc6vsv6t32eu6dhja":"",
                                    "did:plc:vkof2dfgcttmaslwzmv76fhx":"bafkreid3owarkiz4h267ejagds4kxgu3qxj45wbtp4pf75bhku6jcl2xq4",
                                    "did:plc:wg5pgjo2xp5eymgu7guskxht":"bafkreifn2jdeukoyq24bca4te2htakxd3ijvjceqpxh6w24537uuhecvba",
                                    "did:plc:wgiw4zvjhfhhubf6dtocjern":"bafkreibkkfry5co2opt3itgcx3y2dkuqwpy3kzwkmf5b6b7q6i76qutduu",
                                    "did:plc:wvgzdrosihvh23fw3s3vrc2t":"bafkreieukru2l72hdffbnxw722br5x6kexw6wedx5m3exw4wf4kgh6efca",
                                    "did:plc:yjlryeay3f5owqqvnvtc4rjw":"bafkreib5dnce3i4jjtbxbblbjzbagovyr3mjakcl6jnbvtwp6lnzan2xti"
                                }
                        }
            }

### 8.

- **Endpoint:** `/api/v1/anon/lists/block-stats`
  - **Method:** `GET`
    - **Description:** Get a list of block stats based on userbase
    - **Parameters:** None
    - **Response:**
        ```json
            {
                "as of":"2024-04-16T01:41:27.900623",
                    "data":
                        {
                            "averageNumberOfBlocked":{"displayname":"Average Number of Users Blocked","value":5.84},
                            "averageNumberOfBlocks":{"displayname":"Average Number of Blocks","value":"22.09"},
                            "numberBlock1":{"displayname":"Number of Users Blocking 1 User","value":"218,028"},
                            "numberBlocked1":{"displayname":"Number of Users Blocked by 1 User","value":"908,864"},
                            "numberBlocked101and1000":{"displayname":"Number of Users Blocked by 101-1000 Users","value":"9,954"},
                            "numberBlocked2and100":{"displayname":"Number of Users Blocked by 2-100 Users","value":"1,021,503"},
                            "numberBlockedGreaterThan1000":{"displayname":"Number of Users Blocked by More than 1000 Users","value":"880"},
                            "numberBlocking101and1000":{"displayname":"Number of Users Blocking 101-1000 Users","value":"12,653"},
                            "numberBlocking2and100":{"displayname":"Number of Users Blocking 2-100 Users","value":"281,329"},
                            "numberBlockingGreaterThan1000":{"displayname":"Number of Users Blocking More than 1000 Users","value":"751"},
                            "numberOfTotalBlocks":{"displayname":"Number of Total Blocks","value":"11,335,104"},
                            "numberOfUniqueUsersBlocked":{"displayname":"Number of Unique Users Blocked","value":"1,941,201"},
                            "numberOfUniqueUsersBlocking":{"displayname":"Number of Unique Users Blocking","value":"512,761"},
                            "percentNumberBlocked1":{"displayname":"Percent of Users Blocked by 1 User","value":46.82},
                            "percentNumberBlocked101and1000":{"displayname":"Percent of Users Blocked by 101-1000 Users","value":0.51},
                            "percentNumberBlocked2and100":{"displayname":"Percent of Users Blocked by 2-100 Users","value":52.62},
                            "percentNumberBlockedGreaterThan1000":{"displayname":"Percent of Users Blocked by More than 1000 Users","value":0.05},
                            "percentNumberBlocking1":{"displayname":"Percent of Users Blocking 1 User","value":42.52},
                            "percentNumberBlocking101and1000":{"displayname":"Percent of Users Blocking 101-1000 Users","value":2.47},
                            "percentNumberBlocking2and100":{"displayname":"Percent of Users Blocking 2-100 Users","value":54.87},
                            "percentNumberBlockingGreaterThan1000":{"displayname":"Percent of Users Blocking More than 1000 Users","value":0.15},
                            "percentUsersBlocked":{"displayname":"Percent Users Blocked","value":32.86},
                            "percentUsersBlocking":{"displayname":"Percent Users Blocking","value":8.68},
                            "totalUsers":{"displayname":"Total Users","value":"5,906,944"}
                        }
            }

### 9.

- **Endpoint:** `/api/v1/anon/get-list/<handle/did>`
  - **Method:** `GET`
    - **Description:** Get list of moderation lists a user is on
    - **Parameters:** handle or did
    - **Response:**
        ```json
              {
                  "data":
                      {
                          "identifier":"rudyfraser.com",
                              "lists":
                                  [
                                      {"created_date":"2023-11-10T14:48:41.854000+00:00","date_added":"2023-12-07T03:29:19.984000+00:00","description":"To see only porn, block or mute everyone on this list. Ezpz.","handle":"whydoilikethis.bsky.social","list user count":17065,"name":"Not Porn","status":true,"url":"https://bsky.app/profile/did:plc:g2xshwj4o33b5wzxs3xspfxk/lists/3kdtppevxdt2h"},
                                      {"created_date":"2023-07-02T23:46:37.719000+00:00","date_added":"2024-02-24T18:02:24.691000+00:00","description":"Bas3d crypto skeeters","handle":"alkohlmist.bsky.social","list user count":104,"name":"MetaDAOists","status":true,"url":"https://bsky.app/profile/did:plc:dwzmn37bquliunjanpeostli/lists/3jzlaonnxtl2m"},
                                      {"created_date":"2024-02-29T05:41:53.330000+00:00","date_added":"2024-03-01T17:09:31.144000+00:00","description":"","handle":"edavis.dev","list user count":41,"name":"Tech","status":true,"url":"https://bsky.app/profile/did:plc:4nsduwlpivpuur4mqkbfvm6a/lists/3kmjuvrij622k"},
                                      {"created_date":"2023-12-14T13:45:14.015000+00:00","date_added":"2023-12-22T00:45:29.137000+00:00","description":"Your presence here makes a big difference and improves my feeds, thank you!","handle":"scanty.bsky.social","list user count":1449,"name":"Feed Guard \ud83d\udee1\ufe0f","status":true,"url":"https://bsky.app/profile/did:plc:2wt2zjrqtveulc5a2sl2ppgt/lists/3kq3dtinvc32i"},
                                      ...
                                  ]
                      },
                  "identifier":"rudyfraser.com"
              }
      
### 10.

- **Endpoint:** `/api/v1/anon/subscribe-blocks-blocklist/<handle/did>/<page:int>`
  - **Method:** `GET`
    - **Description:** Get list of lists that a user is blocking
    - **Parameters:** handle or did
    - **Response:**
        ```json
            {
                "data":
                    {
                        "blocklist":
                            [
                                {"date_added":"2024-03-11T01:29:10.890000+00:00","handle":"acuarelaazul.bsky.social","list count":15,"list_uri":"at://did:plc:oe5k5kgdudinkw6jpzzfcw4q/app.bsky.graph.list/3kmds77epsk2e","list_url":"https://bsky.app/profile/did:plc:oe5k5kgdudinkw6jpzzfcw4q/lists/3kmdsa2cmuc27","status":true,"subject_did":"did:plc:2b7th5azcseckwqgrq2uyxum"},
                                {"date_added":"2024-03-11T01:29:10.890000+00:00","handle":"nathaliepenaud.bsky.social","list count":15,"list_uri":"at://did:plc:oe5k5kgdudinkw6jpzzfcw4q/app.bsky.graph.list/3kmds77epsk2e","list_url":"https://bsky.app/profile/did:plc:oe5k5kgdudinkw6jpzzfcw4q/lists/3kmdsa2cmuc27","status":true,"subject_did":"did:plc:sa7vi6iwti6oehwj7hqwhuql"},
                                {"date_added":"2024-03-11T01:29:10.890000+00:00","handle":"rafikiscope.bsky.social","list count":15,"list_uri":"at://did:plc:oe5k5kgdudinkw6jpzzfcw4q/app.bsky.graph.list/3kmds77epsk2e","list_url":"https://bsky.app/profile/did:plc:oe5k5kgdudinkw6jpzzfcw4q/lists/3kmdsa2cmuc27","status":true,"subject_did":"did:plc:r7hknu5mmrm4rufgkgcl6et4"},
                                {"date_added":"2024-03-11T01:29:10.890000+00:00","handle":"elosgo.bsky.social","list count":15,"list_uri":"at://did:plc:oe5k5kgdudinkw6jpzzfcw4q/app.bsky.graph.list/3kmds77epsk2e","list_url":"https://bsky.app/profile/did:plc:oe5k5kgdudinkw6jpzzfcw4q/lists/3kmdsa2cmuc27","status":true,"subject_did":"did:plc:byehy3ewhpfk3e47glrhju4y"},
                                ...
                            ],
                        "count":"502",
                        "pages":6
                    },
                "identity":"shreyanjain.net",
                "status":true
            }
      
### 11.

- **Endpoint:** `/api/v1/anon/subscribe-blocks-single-blocklist/<handle/did>/<page:int>`
  - **Method:** `GET`
    - **Description:** Get list of lists that a user is blocked on
    - **Parameters:** handle or did
    - **Response:**
        ```json
            {
                "data":
                    {
                        "blocklist":
                            [
                                {"date_added":"2024-02-27T10:54:12.347000+00:00","did":"did:plc:fmnwe2six767bnsxd7qcr55x","handle":"kaeru.bsky.social","list_uri":"at://did:plc:wixdgg4ejykqrsoqgi7c2fk6/app.bsky.graph.list/3jvltmsuhak2j","list_url":"https://bsky.app/profile/did:plc:wixdgg4ejykqrsoqgi7c2fk6/lists/3jvltmsuhak2j","status":true},
                                {"date_added":"2024-02-12T02:47:20.121000+00:00","did":"did:plc:ky6qvoi6nefhkrtq73k5lu5p","handle":"bunnyofcourage.bsky.social","list_uri":"at://did:plc:wixdgg4ejykqrsoqgi7c2fk6/app.bsky.graph.list/3jvltmsuhak2j","list_url":"https://bsky.app/profile/did:plc:wixdgg4ejykqrsoqgi7c2fk6/lists/3jvltmsuhak2j","status":true},
                                {"date_added":"2024-02-11T08:02:23.578000+00:00","did":"did:plc:fysguxhym4cjnsykyrlvp67j","handle":"5p34r.bsky.social","list_uri":"at://did:plc:wixdgg4ejykqrsoqgi7c2fk6/app.bsky.graph.list/3jvltmsuhak2j","list_url":"https://bsky.app/profile/did:plc:wixdgg4ejykqrsoqgi7c2fk6/lists/3jvltmsuhak2j","status":false},
                                {"date_added":"2024-02-07T20:37:09.031000+00:00","did":"did:plc:pv52siaeqdc3ib64nbcm7q3n","handle":"animationiskey.bsky.social","list_uri":"at://did:plc:wixdgg4ejykqrsoqgi7c2fk6/app.bsky.graph.list/3jvltmsuhak2j","list_url":"https://bsky.app/profile/did:plc:wixdgg4ejykqrsoqgi7c2fk6/lists/3jvltmsuhak2j","status":true},
                                ...
                            ],
                        "count":"9",
                        "pages":1
                    },
                "identity":"thieflord.dev",
                "status":true
            }

### 12.

- **Endpoint:** `/api/v1/anon/lists/dids-per-pds`
  - **Method:** `GET`
    - **Description:** Return a list of the count of users on each PDS
    - **Parameters:** None
    - **Response:**
        ```json
            {
                "data":
                    {
                        "https://42d.fr":1,"https://465789.xyz":1,
                        "https://80px.org":3,
                        "https://afternooncurry.com":1,
                        "https://agaric.us-west.host.bsky.network":276517,
                        ...
                    }
            }

### 13.

- **Endpoint:** `/api/v1/anon/get-moderation-list/<name:string>`
  - **Method:** `GET`
    - **Description:** Get a list of lists and other details based on word search of either the list name or description
    - **Parameters:** name
    - **Response:**
        ```json
            {
                "data":
                    {
                        "lists":
                            [
                                {"created_date":"2023-11-10T21:06:44.219000+00:00","description":"","handle":"vulpido.bsky.social","list count":11,"name":"developers","status":true,"url":"https://bsky.app/profile/did:plc:dowd32x5rh3nqqkqeseayutn/lists/3kduetbtkut2f"},
                                {"created_date":"2023-12-29T11:34:03.625000+00:00","description":"and designers","handle":"yukotan.bsky.social","list count":55,"name":"developers","status":true,"url":"https://bsky.app/profile/did:plc:qexgypv67x75g7bjrelr5gof/lists/3kholoh6fa32m"},
                                {"created_date":"2024-02-09T19:31:00.653000+00:00","description":"","handle":"nklocal.bsky.social","list count":3,"name":"BlueskyDeveloper","status":true,"url":"https://bsky.app/profile/did:plc:wkqs6vwhryiinw35pcfwmrfg/lists/3kmmamibzcu2y"},
                                {"created_date":"2024-02-11T18:24:43.639000+00:00","description":null,"handle":"blaisealicki.bsky.social","list count":11,"name":"Developers","status":true,"url":"https://bsky.app/profile/did:plc:sbigafqky4xbshjw33qg6thx/lists/3kl5x5b566q2a"},
                                ...
                            ],
                        "pages":7
                    },
                "input":"dev"
            }
      
### 14.

- **Endpoint:** `/api/v1/anon/get-handle-history/<handle/did>`
  - **Method:** `GET`
    - **Description:** Get the account history of a user
    - **Parameters:** handle or did
    - **Response:**
        ```json
            {
                "data":
                    {
                        "handle_history":
                        [
                            ["rudyfraser.com","2023-11-13T02:37:31.907Z","https://shiitake.us-east.host.bsky.network"],
                            ["rudyfraser.com","2023-05-25T12:22:54.104Z","https://bsky.social"],
                            ["salesforce.herokuapp.com","2023-05-04T00:32:48.659Z","https://bsky.social"],
                            ["rudyfraser.herokuapp.com","2023-05-04T00:29:38.207Z","https://bsky.social"],
                            ["rudyfraser.com","2023-05-02T16:05:34.405Z","https://bsky.social"],
                            ["shacqeal.bsky.social","2023-05-01T03:43:42.434Z","https://bsky.social"]
                            ...
                        ],
                        "identifier":"rudyfraser.com"
                    }
            }

### 15.

- **Endpoint:** `/api/v1/anon/images/logo`
  - **Method:** `GET`
    - **Description:** Get the logo image
    - **Parameters:** None
    - **Response:** png

### Authenticated:

For information about authenticated endpoints please contact us at [support@clearsky.app](mailto:support@clearsky.app)