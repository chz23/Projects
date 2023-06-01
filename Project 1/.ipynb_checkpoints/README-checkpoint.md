# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Exploring climate data of Singapore

## Problem Statement

Event cancellations in Singapore often occur as a result of adverse weather, more specifically, rain. This poses an issue to People's Association, which plans numerous events to engage Singaporeans from all walks of life. This project aims to analyse and identify monthly weather patterns so that People's Association staff will be able to plan events around the local weather more effectively, thus resulting in fewer event cancellations.

## Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|month|_object (str)_|N.A.|Month as 2-digit numbers|
|maximum_rainfall_in_a_day|_float_|rain_max_in_day_monthly|Total rainfall in the wettest day of the month (unit: mm)|
|no_of_rainy_days|_int_|rain_days_monthly|Number of rainy days|
|total_rainfall|_float_|rain_total_monthly|Total rainfall (unit: mm)|
|mean_humidity|_float_|humidity_mean_monthly|Mean relative humidity (unit: %)|
|mean_sunshine_hrs|_float_|sunshine_daily_mean_monthly|Mean number of hours of sunshine|
|mean_temp|_float_|temp_mean_monthly|Mean temperature (unit: °C)|
|total_days|_int_|N.A.|Number of days in the specified month|

## Summary of Analysis

### Correlation between rainfall and other weather variables

Rainfall is fairly positively correlated with humidity. The higher the humidity, the higher the rainfall rate.

Rainfall is somewhat inversely correlated with temperature. The higher the temperature, the lower the rainfall rate. However, this is not seen across all months.

Rainfall is strongly inversely correlated with hours of sunshine. The higher the number of hours of sunshine, the lower the rainfall rate.

### Overview of months

The rainy season takes place from Oct to Dec. These months feature the highest rainfall rates (number of rainy days divided by total number of days) as well as total rainfall. It rains often and heavily, with consecutive periods of rain being rather common. Weather is stable and predictable, and the abovementioned correlations tend to be true of this period, ie. these months are usually wet, humid, cooling and cloudy.

Apr to Sep are the 'in-between' period in terms of rainfall, with a few patterns being noticeable within this period itself. For example, from Apr to May, Sumatra Squalls account for quite a number of rainy periods, and these showers tend to take place in predawn or morning. This period also includes the hottest stretch of the year from Apr to May.

Jan to Mar are the driest as well as most unpredictable months of the year. Rainfall can vary a lot from year to year, and humidity and temperature can also defy expectations at times. This is due to an additional factor being crucial in determining weather for these months: the Northeast Monsoon.

### Northeast Monsoon

This period (Dec - early Mar) can be split into 2 parts, with the first half of the season being wet and the second half being dry. The monsoon phenomenon is essentially a rain-belt that shifts across Asia. Thus, it doesn't 'strike' a country on a specific day. Instead, it comes gradually and not always consistently. By Jan, the rain-belt should have moved on, leaving behind strong winds and a dry period. This explains why Jan - Mar can experience a lot of volatility - for example, in a year when the monsoon is 'delayed', these months will most likely be significantly wetter than usual.

On the other hand, Dec is always stable because while the monsoon is considered to 'commence' in Dec, in reality, the rainy season starts in Oct. By the time Nov and Dec come round, the rainy season is at its peak, ie. they are almost never affected by delays in monsoon periods or otherwise.

## Conclusions & Recommendations

### Outdoor activities

#### Oct: start of the rainy season

Cool, wet conditions are typically expected as the year nears the later months; Oct typically marks the start of the rainy season. It has a much lower rainfall rate compared to Nov and Dec, but it's still above the average rainfall rate. Continuing on from Sep, rainfall becomes heavier once October hits, and storms typically strike during afternoons and early evenings. In addition, some volatility is expected since there is no 'official' or exact start to the monsoon period.

#### Avoid the rainiest months - Nov & Dec

Both months have _consistently_ proven to be the wettest of all months. In addition, both months tend to experience moderate to heavy rainfall that goes on continuously over consecutive days, sometimes lasting up to a week! If complete avoidance is not possible, especially since it's for an entire 2-month stretch, consider the following:
- Create ample wet weather plans while keeping in mind that they are, more likely than not, going to be used.
- Create flexible schedules that involve both indoor and outdoor activities, preferably in an interchangeable manner.
- Simplify schedules & avoid being over-ambitious - Dec is a popular month for travelling anyway.
    
#### Jan is a fairly unpredictable month - tread with caution

As the tail-end of the wet season, Jan's lack of predictability is unsurprising, since the exact start & end of monsoon seasons are not set in stone. Consider the following mitigating measures:
- Keep the schedule for Jan largely interchangeable; weather patterns, while not obvious way ahead of time, may potentially be more predictable when it's closer to the actual month. Having a good mix of outdoors and indoors activities for the month makes it easier to swap them out for one another.
- Schedule outdoor activities towards the tail-end of the month when the dry season is slated to begin.
- Have a few solid wet weather plans on hand:
    - Despite being the third driest season on paper, there's actually still a 43% chance of rain on any given day!
    - The rainiest day in January is often one of the rainiest days in the entire year as well - if this is the day of the activity, the wet weather plan will most certainly need to be used.

Being the start of the year, Jan is typically when people feel the most motivated to 'up' their fitness game or kickstart a new and improved lifestyle. We can further encourage this by planning fitness events that can take place rain or shine, ie. mostly indoors.

#### Feb is the most unpredictable month of all, but rainfall rates are low enough that a gamble will probably be worth it

In addition to having the lowest rainfall rate, when it does rain, it's likely to be fairly manageable. Unlike Jan, the rainiest day in Feb is probably just an average shower. It is one of the cooler months as well - it had a mean surface air temperature of <= 27.5 degrees celsius more than 80% of the time! During dry weather, it is great for more strenuous / long / large-scale outdoor activities such as hiking, mass running events, beach clean-up, outdoor performances, etc. Feb is likely most affected by what the year is going to be like in general (some years are just wetter overall). For an average year, planning as per normal with 1 or 2 wet weather plans on hand should suffice.

#### Mar - like Jan, but slightly better

The unpredictability of Mar comes from it being the tail-end of the monsoon season. As the month progresses, it may get hotter, less windy, and more prone to afternoon/evening showers. There's an opportunity to take advantage of the drier, more cooling weather in the beginning part of March. Technically, a dry day in March would be ideal for more 'intense' outdoor activities, such as an outing to the beach or botanical gardens, but keep in mind that the tail-end of the monsoon season will inherently be slightly uncertain. Schedule outdoor activities in the beginning of the month when the dry season is still likely to be in full force.

#### Apr & May: surprisingly hot (especially in the afternoons)

Both also have higher rainfall rates compared to Jun/Jul/Sep. Occasional thunderstorms in the afternoons may last till early evening. Hot & potentially rainy, with above-average humidity levels, there's a need to plan for a greater variety of events during these months & keep them largely interchangeable so that they can be altered when more accurate information pours in, for example from the meteorological agency. 

#### Jun, Jul & Sep: good for casual outdoor activities

These months typically experience low rainfall rates, although still higher than the Jan - Mar period. When it does rain, showers are likely to be moderate. There's a chance that they will take place in the afternoon but typically won't last too long. Being near sheltered areas in the afternoons may be helpful in case of temporary rainy weather. Alternatively, reminding participants to bring umbrellas may be sufficient as well, depending on the nature of the activity.

Jun & Jul also tend to be sunnier / hotter while Sep typically experiences more moderate temperatures. Outdoor activities can ideally be held during these months, but try to avoid overly-strenuous activities due to the possibility of hot weather in Jun & Jul, especially if the target group is the elderly. On the other hand, Sep should be cooling enough for such activities!

Jun is also the month of school holidays although families are less likely to travel during Jun than Dec. Some family-bonding activities can be planned for, especially at the CC-level to avoid complicated logistics for overly huge crowds. Examples include:
- Treasure hunt, involving a mixture of outdoor & indoor activities.
- Educational trips such as farm trips, visiting the botanical gardens, going on a history trail (points-based to entice the children, mixture of indoor & outdoor locations)

#### Aug: the month of moderation

Aug boasts of an average rainfall rate, slightly above-average temperatures, as well as being the least humid month of all. Part of the Southwest Monsoon period alongside Jun, Jul & Sep, Aug is pretty similar to these months but historically wetter. Humidity levels are low though, which may make outdoor activities more tolerable/pleasant. Since Aug includes National Day, this is the prime time to engage citizens on a CC/RC level, such as block decoration activities, etc. To spice things up, competitons can be held.


Apart from the wet conditions, October generally has a moderate climate in terms of temperature and humidity levels. From this month onwards, it would be good to plan for more indoor activities. If outdoors activities must be planned, try to restrict them to just the first week.

#### [It's Always Sunny in Philadelphia](https://en.wikipedia.org/wiki/It%27s_Always_Sunny_in_Philadelphia), but It's Always Rainy in Singapore
_and hot...and humid..._

11 out of 12 months have average rainfall rates exceeding 40% - this means that each week typically experiences at least 2 to 3 days of rain! Giving up on outdoor activities is clearly not the answer - keep in mind that, even on rainy days, there are differences. For example, rain isn't '24/7' - different periods have different 'rainy hours'. Nov to Jan (especially early Jan) should be avoided not just because of high rainfall rates, but also because it tends to rain in the afternoon / early evening with the potential for storms to persist for long periods, and over many days!

Another example would be the 'middle months' - while they tend to appear similar, there's a difference.  Mar - May tends to experience showers in the afternoon & early evening, since they are in the inter-monsoon period following the Northeast Monsoon. On the other hand, Jun - Sep (Southeast Monsoon) often experience rains before dawn and during midday due to Sumatra Squalls. Some short ('passing') showers happen in the afternoon as well. Using the Southeast Monsoon period as an example, passing showers may not necessitate a complete shift in plans whereas prolonged rain would.

Different precautionary measures should be put in place depending on the month - an outdoor activity held during the rainy season may require a well-crafted wet weather plan that has a high probability of being used, whereas one held during a month typically experiencing short, light showers probably just needs reminders to bring umbrellas/raincoats and smart planning that would have participants take their breaks in sheltered areas during predicted rainy hours.

Outdoors activities also differ widely - a hike to Bukit Timah Hill should definitely be organised during a cool, dry period whereas a walk around the estate with stops at various points of interest can probably be planned for in most months.