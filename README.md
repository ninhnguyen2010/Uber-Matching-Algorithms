# Uber-Matching-Algorithms
<img src="https://ei.marketwatch.com/Multimedia/2016/08/01/Photos/NS/MW-ES907_didi_u_20160801154402_NS.jpg?uuid=4c17b2d4-5820-11e6-8568-0015c588dfa6">

<h1>Ride-Hailing Platforms</h1>
<br>
<font size="+1">
    <ul>
        <li>Ride-hailing platforms such as Uber, Lyft, and DiDi have achieved explosive growth and reshaped urban transportation.</li>
        <br>
        <ul>
            <li>For example, Uber has completed over 10 billion trips globally and is active in over 80 countries and 700 cities since its initial launch in 2009.</li>
            <br>
            <li>By some estimates, the global ride-hailing industry is projected to grow to a 285-billion dollar total market value by 2030.</li>
            <br>
        </ul>
        <li>Ride-hailing platforms connect riders and drivers via a <i>centralized</i> and <i>automated matching and pricing system</i> in a <b>two-sided marketplace</b>.</li>
        <br>
        <li>Ride-hailing platforms have three components:</li>
        <br>
        <ul>
            <li>driver app (for drivers to offer services and communicate with their customers),</li>
            <br>
            <li>rider app (for customers to book and track their journeys and select vehicle types),</li>
            <br>
            <li>and a dispatch system (a system that connects the driver and the customer via their mobile phones).</li>
            <br>
        </ul>
        <li>Relative to taxi services, drivers participating in ride-hailing platforms spend a higher proportion of their time delivering rides.</li>
        <br>
        <ul>
            <li>This is known as having a higher <b><i>capacity utilization rate</i></b>.</li>
            <br>
            <li>In other words, UberX drivers spend less time waiting between ride requests or driving to pick up riders, compared to taxi drivers.</li>
            <br>
            <li>This is typically true on the driver side as well.</li>
            <br>
            <li>Many studies have been conducted and they have found that the average rider waiting time between request and pickup (known as <b><i>rider waiting time</i></b>) can be much lower in a ride-hailing system compared to a street-hailing system.</li>
            <br>
        </ul>
        <li style="color:blue">The are two key levers in building a successful ride-hailing platform:</li>
        <br>
        <ul style="color:blue">
            <li>matching algorithms, which help to efficiently match riders and drivers,</li>
            <br>
            <li>and dynamic pricing algorithms, which help to keep the supply of drivers and demand of riders in balance.</li>
            <br>
        </ul>
        <li>Matching refers to the process of dispatching available drivers to pick up riders.</li>
        <br>
        <ul>
            <li><img src="https://www.uber-assets.com/image/upload/f_auto,q_auto:eco,c_fill,w_956,h_637/v1611193266/assets/58/69b90b-b3a6-412f-a45e-4a28026cd86a/original/2_Better-matching-matters-grey.jpg" width="300"></li>
            <br>
        </ul>
        <li>Dynamic pricing refers to the adjustment of prices for rides over time based on real-time demand and supply conditions.</li>
        <br>
        <ul>
            <li>Dynamic pricing is called <i>surge pricing</i> by Uber and <i>prime time</i> by Lyft.</li>
            <br>
            <li><img src="https://pbs.twimg.com/media/FQJrV5LXIAAclOb?format=jpg&name=900x900" height="300" width="300"></li>
            <br>
        </ul>
        <li>A successful implementation of matching and pricing can be leveraged to create an experience with <b>low waiting times</b> for both riders and drivers.</li>
        <br>
        <li style="color:dodgerblue">As an aside:</li>
        <br>
        <ul style="color:dodgerblue">
            <li>Matching and dynamic pricing algorithms have been leveraged by many other online platforms that connect service providers and consumers.</li>
            <br>
            <li>For example,</li>
            <br>
            <ul>
                <li><a href="https://www.taskrabbit.com/blog/unveiling-the-new-taskrabbit">TaskRabbit</a> for chores and home projects,</li>
                <br>
                <li><a href="https://www.ebay.com/help/selling/listings/listing-tips/optimising-listings-best-match?id=4166">eBay</a> for e-commerce,</li>
                <br>
                <li><a href="https://www2.aueb.gr/users/mitsopoulou/files/Parking_Percom_camera_ready(1).pdf">SpotHero</a> for parking spaces,</li>
                <br>
                <li>StubHub for concert and sports game tickets,</li>
                <br>
                <li>Turo and Getaround for car-sharing,</li>
                <br>
                <li>and <a href="https://blogs.cornell.edu/info4220/2016/03/18/how-airbnb-uses-matching-markets-to-ensure-host-preferences/">Airbnb</a> for hospitality services.</li>
                <br>
            </ul>
            <li>In contrast to ride-hailing, these services provide matching <i>suggestions</i> and price <i>guidance</i> via recommendation systems, but the final decisions are made by the participants on the platform as opposed to the platform itself.</li>
            <br>
            <li>Food and grocery delivery platforms (such as UberEats, Instacard, or Grubhub) are more similar to ride-hailing platforms, but they have more time and flexibility for dispatching due to a lower level of urgency for the service.</li>
            <br>
            <li>The pricing and matching decisions for ride-hailing services need to be resolved in real-time as riders and drivers are sensitive in time.</li>
            <br>
            <li>Matching and pricing algorithms are both optimization problems!</li>
            <br>
        </ul>
    </ul>
</font>

<hr style="border:10px solid black">

<h2><a href="https://www.uber.com/blog/engineering-routing-engine/">Brief History of Uber's Routing Engine and Technological Innovation</a></h2>
<br>
<font size="+1">
    <ul>
        <li>When the Uber app was initially launched around 2010, one of the first features of the app was the ETA (estimated time of arrival) between you and the closest driver.</li>
        <br>
        <li>In the early days, Uber used a combination of different routing engines to produce an ETA, including the <a href="http://project-osrm.org/">Open Source Routing Machine (OSRM)</a>, which is an open source optimal routing package and the entire codebase can be found on <a href="https://github.com/Project-OSRM">GitHub</a>.</li>
        <br>
        <ul>
            <li>Also in the early days, Uber didn't have navigation available in the app, so the app was only used to estimate the ETA and to display vehicle locations.</li>
            <br>
            <li>This service of estimating ETAs was called <i>"GoldETA"</i> and it was a model that was built on top of the routing engines and adjusted the original estimates using Uber's historical data of similar routes.</li>
            <br>
            <li>This solution ultimately took into account hundreds of thousands of Uber trips and compared them to the initial routing engine's ETA.</li>
            <br>
            <li>GoldETA worked better than using any single ETA estimate alone.</li>
            <br>
        </ul>
        <li>The main challenge was the <a href="https://en.wikipedia.org/wiki/Cold_start_(recommender_systems)">cold start</a> problem that Uber faced when they launched in new cities.</li>
        <br>
        <ul>
            <li>Specifically, the cold start problem refers to when you want to use a model without having estimated the model on relevant data, that is, your model starts <i>cold</i>.</li>
            <br>
        </ul>
        <li>Additionally, as Uber grew, they needed to add features to their platform that became difficult to implement due to the integration with the open source codebase OSRM.</li>
        <br>
        <li>These challenges led Uber to develop their own routing engine solution.</li>
        <br>
        <li>This required better ETA prediction and better matching and pricing optimization algorithms.</li>
        <br>
        <li>For more on this development, see <a href="https://www.uber.com/blog/engineering-routing-engine/">this link</a>.</li>
        <br>
    </ul>
</font>

<hr style="border:10px solid black">

<h2>Matching in Ride-Hailing</h2>
<br>
<font size="+1">
    <ul>
        <li>Rides can be either non-shared, meaning that the ride is arranged for only one customer group, or shared, meaning that several customer groups with different pickup and dropoff locations share the ride.</li>
        <br>
        <li>In the simpler case of a non-shared ride, drivers participating on the platform cycle through three states sequentially: </li>
        <br>
        <ul>
            <li><i>"open"</i> (waiting to be dispatched),</li>
            <br>
            <li><i>"en route"</i> (on the way to the pickup location),</li>
            <br>
            <li>and <i>"on-trip"</i> (driving riders to their destination).</li>
            <br>
        </ul>
        <li>A request can be matched with a dispatchable driver using very simple algorithms, such as the <b><i>first-dispatch protocol</i></b>.</li>
        <br>
        <ul>
            <li>In the first-dispatch protocol only open drivers are considered as dispatchable.</li>
            <br>
            <li>Each request is immediately assigned to the open driver who is predicted to have the shortest en route time.</li>
            <br>
            <li>This matching algorithm is also called the <i>on-call</i> policy, the <i>closest driver</i> policy, and the <i>committed driver-rider</i> matching protocol.</li>
            <br>
        </ul>
        <li>An alternative matching approach is <i>batching</i> where rider requests are collected for a short time window (typically on the order of seconds), at the end of which an optimization problem is solved to pair each request with an open driver.</li>
        <br>
        <li>If there are riders that are not matched in this batch, then they are carried over and used for the optimization problem in the next batching window.</li>
        <br>
        <li>Batching can reduce the rider waiting time relative to the <i>first-dispatch</i> protocol by consolidating requests and making better use of supply.</li>
        <br>
        <ul>
            <li>Note that the first-dispatch protocol can be viewed as a special case of the batching protocol when each batch consists of exactly one rider request.</li>
            <br>
        </ul>
        <li>Due to its substantial benefits, batching has been implemented widely in major ride-hailing platforms.</li>
        <br>
    </ul>
</font>
