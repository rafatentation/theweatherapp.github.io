Sizler için Hava Durumu uygulaması yaptım.
İlk olarak Node.JS uygulamasını indirmeniz gerekiyor. Daha sonra "Terminal" kısmına "create-react-app the-weather-api" yazmanız lazım. Böylece React App yükleniyor ve daha sonra terminal kısmına "npm start" yazıyoruz. React uygulamasının tüm dosyları indiriliyor.

İlk önce "www.weatherapi.com" sitesinde hesab açıyoruz, ordan API Expolorer`de 3 günlük hava durumunu seçtikden sonra API Key`i kopyalıyoruz:
" function App()
                        const APP_KEY = "e0af464eeaa245ed9e6232017221912"
                        let cityinput2=""
                        const [wheatherdata, setwheatherdata]=useState([])
                        function citytext() "


Link olarak sitenin linkini yazıyoruz ve böylece tüm şehirlerin 3 günlük hava durumu aktif oluyor:
 if (value==="") return;
                            const data=await fetch(`http://api.weatherapi.com/v1/forecast.json?key=${APP_KEY}&q=${value}&days=3&aqi=no&alerts=no`)
                            const result = await data.json();
                            setwheatherdata(result.forecast.forecastday)
                          console.log(result.forecast.forecastday)  
                          
                         
 "src" klasörünün içinde yeni dosya açıyoruz - "weatherresult.js" ve bu kodu yazıyoruz - böylece temprature, icon, tarih aktif oluyor:
 import React from 'react'
                                import './wheather.css'
                                function Wheatherresult({date,mintemp,maxtemp,condition,icon}) {
                                    return (
                                    div className="result"
                                            h2 {date} /h2
                                            ul
                                                li><img src={icon} alt=""/> /li>
                                                li>{condition} /li>
                                                li>{mintemp} c / {maxtemp} c /li>
                                            /ul>
                                        /div>
                                    )
                                }
                                export default Wheatherresult
                                
                                
                                
 Bu kısımda istediğiniz şehirleri aratarak hava durumuna kolayca ulaşa bilirsiniz. "Search" butonu için kod:
  div className="search">
                        input type="text" placeholder="Search a city..." onChange={citytext}/>
                          button onClick={()=>getdata(cityinput)}>Search</button>      
                        /div>
                        div>
                      {wheatherdata.map(item=>(<Wheather key={item.date} date={item.date} mintemp={item.day.mintemp_c} maxtemp={item.day.maxtemp_c} condition={item.day.condition.text} icon={item.day.condition.icon}/>))}
                        /div>
                      
                      /div>
                      
                      
                      
 Background olarak internetden aldığım fotoğrafı kullandım:
  * {
                            margin: 100%;
                            padding: 100%;
                            box-sizing: border-box;
                            background-image: url(https://cdn.vuetifyjs.com/images/parallax/material2.jpg);
                           }
                           
                           
                           
ÖZET - Sizler için Hava Durumu uygulaması yaptım. Buradan tüm ülkelerin şehirlerini bölgelerini yazarak 3 günlük hava durumu göre bilirsiniz. Önemli olan kısım Node JS uygulamasını indirmeniz lazım ve React uygulamasını başlatmak lazım. weatherapi.com sitesinde hesab açmak ve verileri aktarmak için linkleri kullanmanız lazım.                           
                          
