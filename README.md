- 👋 Hi, I’m @jedsadaxlv
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
jedsadaxlv/jedsadaxlv is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html>

<head>
    <title>Parcel Sandbox</title>
    <meta charset="UTF-8" />
    <link href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
    <link rel="stylesheet" href="style.css">
</head>

<body>


    <div class="container-main-raking">
        <div id="countdown">
            <div id='tiles'></div>
            <div class="labels">
            </div>


            <div class="nav-main-container">
                <button class="col-3" onclick="openElementList('Credit')">Credit</button>
                <button class="col-3" onclick="openElementList('TurnOver')">Turn Over</button>
                <button class="col-3" onclick="openElementList('Affiliate')">Affiliate</button>
            </div>

            <div id="app">
                <div id="Credit" class="col active">
                    <!-- <pre>
                        {{creditList}}
                    </pre> -->
                    <h1 class="text-xl font-semibold mb-1">Credit Ranking</h1>
                    <div class="table w-full">
                        <div class="table-header-group">
                            <div class="table-cell bg-red-500 text-white p-2 text-center">No.</div>
                            <div class="table-cell bg-red-500 text-white p-2">Account API</div>
                            <!-- <div class="table-cell bg-red-500 text-white p-2">Player Name</div> -->
                            <div class="table-cell bg-red-500 text-white p-2">Summary Money</div>
                            <div class="table-cell bg-red-500 text-white p-2">Reward</div>
                        </div>
                        <div class="table-row-group">
                            <div v-for="(item, index) in creditList" :key="index" class="table-row">
                                <div class="table-cell bg-red-300 text-white text-center">{{ index + 1 }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.account_api }}</div>
                                <!-- <div class="table-cell bg-red-300 text-white">{{ item.player_name }}</div> -->
                                <div class="table-cell bg-red-300 text-white">{{ item.summary_money }}</div>
                                <div id="demo" class="table-cell bg-red-300 text-white"></div>
                            </div>
                        </div>
                    </div>
                </div>

                <div id="TurnOver" class="col active" style="display:none">
                    <h1 class="text-xl font-semibold mb-1 mt-3">TurnOver Ranking</h1>
                    <div class="table w-full">
                        <div class="table-header-group">
                            <div class="table-cell bg-red-500 text-white p-2 text-center">No.</div>
                            <div class="table-cell bg-red-500 text-white p-2">Account API</div>
                            <div class="table-cell bg-red-500 text-white p-2">Summary turn slot</div>
                            <div class="table-cell bg-red-500 text-white p-2">Summary turn casino</div>
                            <div class="table-cell bg-red-500 text-white p-2">Summary turn other</div>
                            <div class="table-cell bg-red-500 text-white p-2">Summary turn over</div>
                        </div>
                        <div class="table-row-group">
                            <div v-for="(item, index) in turnOverList" :key="index" class="table-row">
                                <div class="table-cell bg-red-300 text-white text-center">{{ index + 1 }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.account_api }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.summary_turn_slot }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.summary_turn_casino }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.summary_turn_other }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.summary_turn_over }}</div>
                            </div>
                        </div>
                    </div>
                </div>

                <div id="Affiliate" class="col active" style="display:none">
                    <h1 class="text-xl font-semibold mb-1 mt-3">Affiliate Ranking</h1>
                    <div class="table w-full">
                        <div class="table-header-group">
                            <div class="table-cell bg-red-500 text-white p-2 text-center">No.</div>
                            <div class="table-cell bg-red-500 text-white p-2">Account API</div>
                            <!-- <div class="table-cell bg-red-500 text-white p-2">Player name</div> -->
                            <div class="table-cell bg-red-500 text-white p-2">Count affiliate</div>
                            <div class="table-cell bg-red-500 text-white p-2">Phone number</div>
                            <div class="table-cell bg-red-500 text-white p-2">Level</div>
                            <div class="table-cell bg-red-500 text-white p-2">Refer code</div>
                        </div>
                        <div class="table-row-group">
                            <div v-for="(item, index) in affiliateList" :key="index" class="table-row">
                                <div class="table-cell bg-red-300 text-white text-center">{{ index + 1 }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.account_api }}</div>
                                <!-- <div class="table-cell bg-red-300 text-white">{{ item.fname + ' ' + item.lname }}</div> -->
                                <div class="table-cell bg-red-300 text-white">{{ item.count_affiliate }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.telephone }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.level }}</div>
                                <div class="table-cell bg-red-300 text-white">{{ item.refer_code }}</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>


    <script src="https://cdn.jsdelivr.net/npm/vue@2"></script>

    <script>
        // function tabs        
        function openElementList(ElementList) {
            var i;
            var x = document.getElementsByClassName("active");
            for (i = 0; i < x.length; i++) {
                x[i].style.display = "none";
            }
            document.getElementById(ElementList).style.display = "block";
        }

        //function coundown 
        var target_date = new Date().getTime() + (1000 * 3600 * 168); // set the countdown date
        var days, hours, minutes, seconds; // variables for time units

        var countdown = document.getElementById("tiles"); // get tag element

        getCountdown();

        setInterval(function () { getCountdown(); }, 1000);

        function getCountdown() {

            // find the amount of "seconds" between now and target
            var current_date = new Date().getTime();
            var seconds_left = (target_date - current_date) / 1000;

            days = pad(parseInt(seconds_left / 86400));
            seconds_left = seconds_left % 86400;

            hours = pad(parseInt(seconds_left / 3600));
            seconds_left = seconds_left % 3600;

            minutes = pad(parseInt(seconds_left / 60));
            seconds = pad(parseInt(seconds_left % 60));

            // format countdown string + set tag value
            countdown.innerHTML = "<span>" + days + "</span><span>" + hours + "</span><span>" + minutes + "</span><span>" + seconds + "</span>";
        }

        function pad(n) {
            return (n < 10 ? '0' : '') + n;
        }


    </script>

    <!-- function api  -->
    <script>

        const fakeinfo = [
            {
                No: 16,
                accountapi: '29tv011146595x',
                SummaryMoney: '245873',
            },
            {
                No: 17,
                accountapi: '29tv011146595xx',
                SummaryMoney: '245873xx',
            }
        ];
        fakeinfo.push({
            No: 18,
                accountapi: '29tv011146595xxa',
                SummaryMoney: '245873xxx',
        });
        console.log(fakeinfo);

        new Vue({
            el: '#app',
            data: {
                setting: {
                    apiURL: 'https://6143bb5f411c860017d251f4.mockapi.io/ranking'
                },
                ranking: {}
            },
            computed: {
                creditList() {
                    return this.ranking?.credit || []
                },
                turnOverList() {
                    return this.ranking?.turn_over || []
                },
                affiliateList() {
                    return this.ranking?.affiliate || []
                },
            },
            async created() {
                this.ranking = await this.fetchRanking()
            },
            methods: {
                async fetchRanking() {
                    try {
                        const response = await fetch(this.setting.apiURL)
                        return await response.json()
                    } catch (error) {
                        return Promise.reject(error)
                    }
                },
            }
        })
    </script>
</body>

</html>
.nav-main-container {
    width: 100%;
    background: gray;
    padding: 20px;
    text-align: center;
}

button {
    border: 2px solid #000;
    padding: 20px;
    border-radius: 8px;
}

/* countdown */
#countdown{
    text-align: center;
    padding: 20px 0px 20px 0px;
}

#countdown:before{
	content:"";
	width: 8px;
	height: 65px;
	background: #444;
	background-image: -webkit-linear-gradient(top, #555, #444, #444, #555); 
	background-image:    -moz-linear-gradient(top, #555, #444, #444, #555);
	background-image:     -ms-linear-gradient(top, #555, #444, #444, #555);
	background-image:      -o-linear-gradient(top, #555, #444, #444, #555);
	border: 1px solid #111;
	border-top-left-radius: 6px;
	border-bottom-left-radius: 6px;
	display: block;
	position: absolute;
	top: 48px; left: -10px;
}

#countdown:after{
	content:"";
	width: 8px;
	height: 65px;
	background: #444;
	background-image: -webkit-linear-gradient(top, #555, #444, #444, #555); 
	background-image:    -moz-linear-gradient(top, #555, #444, #444, #555);
	background-image:     -ms-linear-gradient(top, #555, #444, #444, #555);
	background-image:      -o-linear-gradient(top, #555, #444, #444, #555);
	border: 1px solid #111;
	border-top-right-radius: 6px;
	border-bottom-right-radius: 6px;
	display: block;
	position: absolute;
	top: 48px; right: -10px;
}

#countdown #tiles{
	position: relative;
	z-index: 1;
    padding: 20px;
}

#countdown #tiles > span{
	width: 92px;
	max-width: 92px;
	font: bold 48px 'Droid Sans', Arial, sans-serif;
	text-align: center;
	color: #111;
	background-color: #ddd;
	background-image: -webkit-linear-gradient(top, #bbb, #eee); 
	background-image:    -moz-linear-gradient(top, #bbb, #eee);
	background-image:     -ms-linear-gradient(top, #bbb, #eee);
	background-image:      -o-linear-gradient(top, #bbb, #eee);
	border-top: 1px solid #fff;
	border-radius: 3px;
	box-shadow: 0px 0px 12px rgba(0, 0, 0, 0.7);
	margin: 0 7px;
	padding: 18px 0;
	display: inline-block;
	position: relative;
}
