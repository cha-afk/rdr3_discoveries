# Blip Modifiers

- [Skip to Usage](#usage)
- [Skip to Details](#details)
- [Skip to Examples](#examples)

## Usage

```lua
local function CreateBlip(style, coords, modifiers, name)
  -- The blip's style is the base styling which can then be overridden by modifiers and natives
  local blip = BlipAddForCoords(style, coords.x, coords.y, coords.z)

  -- The modifier actions are applied in order, with natives respecting that order
  -- In this case, we are applying modifiers in order and then overriding the name below
  for _, modifier in ipairs(modifiers) do
    BlipAddModifier(blip, modifier)
  end

  -- Always override the blip name last after applying modifiers
  SetBlipName(blip, name)
end

-- Don't forget to remove the blip after you're done!
CreateBlip(
  `BLIP_STYLE_SHOP`,
  vector3(2508.1557, -1450.2551, 44.6105),
  { `BLIP_MODIFIER_TOD_DAYTIME_ONLY` },
  "Stables"
)
```

## Details

Hashname | Actions
--- | ---
BLIP_MODIFIER_ANIMAL_SKINNED | **Range**:&nbsp;Zoom Level<br>**Transparency**:&nbsp;0.65
BLIP_MODIFIER_AREA | **Category**:&nbsp;`OBJECTIVE_AREA`<br>**Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `EntityInsideBlip`<br>- Value: `AUTO_MODIFIER_AREA_DIM_WHEN_INSIDE`<br>- StayTrueTimeMS: 100<br>**Inverted&nbsp;State**:&nbsp;No<br>**Transparency**:&nbsp;<br>- Value: 0.55<br>- LayerFlags: `AreaLayer`
BLIP_MODIFIER_AREA_ACCURATE | **Area&nbsp;Style**:&nbsp;`AREA_ACCURATE`
BLIP_MODIFIER_AREA_CLAMPED_PULSE | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- DurationMS: 4,000<br>- Count: 100<br>- FadeInOut: Yes<br>- MinAlpha: 0.5<br>- MaxAlpha: 1
BLIP_MODIFIER_AREA_CONTESTED | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- DurationMS: 0<br>- Count: 100<br>- FadeInOut: Yes
BLIP_MODIFIER_AREA_DIRECTIONAL | **Directional&nbsp;Edge&nbsp;Pointer**:&nbsp;Yes<br>**Icon**:&nbsp;`BLIP_AREA_EDGE_DIRECTIONAL`
BLIP_MODIFIER_AREA_HIDE_ON_INSIDE | **Category**:&nbsp;`OBJECTIVE_AREA`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `EntityInsideBlip`<br>- FadeInTimeMS: 0<br>- StayTrueTimeMS: 0<br>- FadeOutTimeMS: 0<br>- InvertCondition: Yes<br>**Inverted&nbsp;State**:&nbsp;No<br>**Transparency**:&nbsp;<br>- Value: 0.55<br>- LayerFlags: `AreaLayer`
BLIP_MODIFIER_AREA_HIDE_ON_OUTSIDE | **Category**:&nbsp;`OBJECTIVE_AREA`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `EntityInsideBlip`<br>- FadeInTimeMS: 0<br>- StayTrueTimeMS: 0<br>- FadeOutTimeMS: 0<br>**Inverted&nbsp;State**:&nbsp;No<br>**Transparency**:&nbsp;<br>- Value: 0.55<br>- LayerFlags: `AreaLayer`
BLIP_MODIFIER_AREA_OUT_OF_BOUNDS | **Color**:&nbsp;`COLOR_RED`
BLIP_MODIFIER_AREA_PULSE | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- DurationMS: 4,000<br>- Count: 100<br>- FadeInOut: Yes
BLIP_MODIFIER_AREA_TAKEOVER | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- DurationMS: 1,000<br>- Count: 100<br>- FadeInOut: Yes
BLIP_MODIFIER_ATTENTION | **Overlay&nbsp;Icon**:&nbsp;`BLIP_ATTENTION`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_BOUNTY_TARGET_INCAPACITATED | **Range**:&nbsp;Always<br>**Threat&nbsp;Indicator**:&nbsp;<br>- MaxThreatDistance: 0
BLIP_MODIFIER_CAMP_NOT_READY | **Color**:&nbsp;`COLOR_LOW_PRIORITY`<br>**Icon**:&nbsp;`BLIP_AMBIENT_CORPSE`
BLIP_MODIFIER_CHASE | **Conditional&nbsp;Removal**:&nbsp;<br>- ConditionData: `EntityEscaped`<br>- FadeOutTimeMS: 0<br>**Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `EntityEscaped`<br>- Value: `BLIP_MODIFIER_URGENT`
BLIP_MODIFIER_COLLECTIBLE_FULL | **Range**:&nbsp;150
BLIP_MODIFIER_COMPANION_ACTIVITY | **Category**:&nbsp;`OBJECTIVE`<br>**Color**:&nbsp;`COLOR_WHITE`<br>**Scale**:&nbsp;1.15
BLIP_MODIFIER_COMPANION_CONVERSATION | **Color**:&nbsp;`COLOR_RADAR_WRONG_TOD`<br>**Overlay&nbsp;Icon**:&nbsp;`BLIP_ATTENTION`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_COMPANION_DOG | **Scale**:&nbsp;0.8
BLIP_MODIFIER_COMPANION_OBJECTIVE | **Category**:&nbsp;`OBJECTIVE`<br>**Color**:&nbsp;`COLOR_OBJECTIVE`<br>**Scale**:&nbsp;1.15
BLIP_MODIFIER_COMPANION_WOUNDED | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_REVIVE`<br>**Overlay Color:** `COLOR_WHITE`
BLIP_MODIFIER_COMPASS_OBJECTIVE | **Current&nbsp;Objective&nbsp;Marker**:&nbsp;<br>- AllowedMapModes: `RADAR_MODE_MINIMAL`<br>- HidingDistance: 35
BLIP_MODIFIER_CREATOR_FOCUS | **Category**:&nbsp;`CREATOR`
BLIP_MODIFIER_CULL_ON_DEATH | **Conditional&nbsp;Removal**:&nbsp;<br>- ConditionData: `TargetIsDead`<br>- FadeOutTimeMS: 0
BLIP_MODIFIER_DEBUG_BLUE | **Category**:&nbsp;`ENEMY`<br>**Color**:&nbsp;`COLOR_BLUE`<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Icon**:&nbsp;`BLIP_AMBIENT_NPC`<br>**Label**:&nbsp;`BLIP_ENEMY`<br>**Scale**:&nbsp;1
BLIP_MODIFIER_DEBUG_GREEN | **Category**:&nbsp;`ENEMY`<br>**Color**:&nbsp;`COLOR_GREEN`<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Icon**:&nbsp;`BLIP_AMBIENT_NPC`<br>**Label**:&nbsp;`BLIP_ENEMY`<br>**Scale**:&nbsp;1
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_50 | **Range**:&nbsp;50
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_60 | **Range**:&nbsp;60
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_70 | **Range**:&nbsp;70
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_80 | **Range**:&nbsp;80
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_90 | **Range**:&nbsp;90
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_100 | **Range**:&nbsp;100
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_110 | **Range**:&nbsp;110
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_120 | **Range**:&nbsp;120
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_130 | **Range**:&nbsp;130
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_140 | **Range**:&nbsp;140
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_150 | **Range**:&nbsp;150
BLIP_MODIFIER_DEBUG_PINK | **Category**:&nbsp;`ENEMY`<br>**Color**:&nbsp;`COLOR_PINK`<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Icon**:&nbsp;`BLIP_AMBIENT_NPC`<br>**Label**:&nbsp;`BLIP_ENEMY`<br>**Scale**:&nbsp;1
BLIP_MODIFIER_DEBUG_RED | **Category**:&nbsp;`ENEMY`<br>**Color**:&nbsp;`COLOR_RED`<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Icon**:&nbsp;`BLIP_AMBIENT_NPC`<br>**Label**:&nbsp;`BLIP_ENEMY`<br>**Scale**:&nbsp;1
BLIP_MODIFIER_DEBUG_YELLOW | **Category**:&nbsp;`ENEMY`<br>**Color**:&nbsp;`COLOR_YELLOW`<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Icon**:&nbsp;`BLIP_AMBIENT_NPC`<br>**Label**:&nbsp;`BLIP_ENEMY`<br>**Scale**:&nbsp;1
BLIP_MODIFIER_DIRECTION_ONLY | **Current&nbsp;Objective&nbsp;Marker**:&nbsp;<br>- AllowedMapModes: `RADAR_MODE_MINIMAL RADAR_MODE_DEFAULT RADAR_MODE_EXPANDED`<br>**Show&nbsp;GPS&nbsp;Path**:&nbsp;No<br>**Visible&nbsp;On**:&nbsp;Yes
BLIP_MODIFIER_DISTANCE_FADE_LONG | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: No<br>- minAlpha: 0.5<br>- fadeRate: 0.005<br>- startDistance: 600
BLIP_MODIFIER_DISTANCE_FADE_MEDIUM | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: No<br>- minAlpha: 0.5<br>- fadeRate: 0.005<br>- startDistance: 300
BLIP_MODIFIER_DISTANCE_FADE_SHORT | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: No<br>- minAlpha: 0.5<br>- fadeRate: 0.005<br>- startDistance: 150
BLIP_MODIFIER_EAGLE_EYE | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: No<br>- minAlpha: 0.027<br>- fadeRate: 0.05<br>- startDistance: 20<br>**Range**:&nbsp;75
BLIP_MODIFIER_ENEMY | **Color**:&nbsp;`COLOR_ENEMY`<br>**Heading&nbsp;Type**:&nbsp;Off<br>**Height&nbsp;Indicator**:&nbsp;Yes
BLIP_MODIFIER_ENEMY_AQUATIC | **Color**:&nbsp;`COLOR_ENEMY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `AIBlips`<br>- FadeInTimeMS: 0<br>- StayTrueTimeMS: 1,000<br>- FadeOutTimeMS: 750
BLIP_MODIFIER_ENEMY_CONFRONTING | **Color**:&nbsp;`COLOR_REDDARK`
BLIP_MODIFIER_ENEMY_DISAPPEARING | **Color**:&nbsp;`COLOR_ENEMY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `AIBlips`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_ENEMY_DISAPPEARING_NO_FLEE_CHECKS | **Color**:&nbsp;`COLOR_ENEMY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `AIBlips_NoFlee`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_ENEMY_DISAPPEARING_NO_SCREEN_CHECKS | **Color**:&nbsp;`COLOR_ENEMY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `AIBlips_NoOnScreen`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_ENEMY_FLEEING | **Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `FleeingAndShouldBlink`<br>- Value: `AUTO_ENEMY_FLEEING`<br>- StayTrueTimeMS: 0
BLIP_MODIFIER_ENEMY_GUNSHOTS_FADE_ON_START | **Color**:&nbsp;`COLOR_ENEMY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `Gunshots`<br>- FirstTimeUsesFade: Yes<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_ENEMY_GUNSHOTS_ONLY | **Color**:&nbsp;`COLOR_ENEMY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `Gunshots`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500<br>- StartHidden: Yes
BLIP_MODIFIER_ENEMY_GUNSHOTS_ONLY_DONT_SHOW_LAST | **Color**:&nbsp;`COLOR_ENEMY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `Gunshots_DoNotShowLastPed`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_ENEMY_IMPORTANT | **Heading&nbsp;Type**:&nbsp;Off<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Pulse**:&nbsp;<br>- Count: 4<br>**Range**:&nbsp;Always
BLIP_MODIFIER_ENEMY_IS_ALERTED | **Color**:&nbsp;`COLOR_ENEMY`<br>**Heading&nbsp;Type**:&nbsp;Cone
BLIP_MODIFIER_ENEMY_LOWER_AWARENESS | **Color**:&nbsp;`COLOR_ENEMY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `AIBlips_LowerAwareness`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_ENEMY_MUST_AGGRO | **Color**:&nbsp;`COLOR_FRIENDLY`<br>**Conditional&nbsp;Style&nbsp;List**:&nbsp;<br>- ConditionData: `GotAngry`<br>- OnTrue: `{"Push":["BLIP_MODIFIER_ENEMY"],"Pop":["BLIP_MODIFIER_ENEMY_MUST_AGGRO"]}`
BLIP_MODIFIER_ENEMY_OBJECTIVE | **Category**:&nbsp;`OBJECTIVE`<br>**Color**:&nbsp;`COLOR_ENEMY`<br>**Heading&nbsp;Type**:&nbsp;Off<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Icon**:&nbsp;`BLIP_OBJECTIVE`<br>**Pulse**:&nbsp;<br>- Count: 4<br>**Range**:&nbsp;Always
BLIP_MODIFIER_ENEMY_ON_GUARD | **Color**:&nbsp;`COLOR_ENEMY_UNALERTED`<br>**Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `GotAngry`<br>- Value: `AUTO_ENEMY_ANGRY`<br>**Heading&nbsp;Type**:&nbsp;Cone<br>**Heading Color:** `COLOR_WHITE`
BLIP_MODIFIER_ENEMY_ON_GUARD_DISAPPEARING | **Color**:&nbsp;`COLOR_ENEMY_UNALERTED`<br>**Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `GotAngry`<br>- Value: `AUTO_ENEMY_ANGRY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `AIBlips`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500<br>**Heading&nbsp;Type**:&nbsp;Cone<br>**Heading Color:** `COLOR_WHITE`
BLIP_MODIFIER_ENEMY_STEALTH_KILL | **Color**:&nbsp;`COLOR_ENEMY_UNALERTED`<br>**Heading&nbsp;Type**:&nbsp;Cone<br>**Heading Color:** `COLOR_WHITE`
BLIP_MODIFIER_ENEMY_TARGETED_ONLY | **Color**:&nbsp;`COLOR_ENEMY`<br>**Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `TargetedOnly`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_FADE | **Fade&nbsp;Effect&nbsp;2**:&nbsp;<br>- FadeOutTimeMS: 1,000<br>- DoActionOnPop: Yes<br>- FadeInTimeMS: 1,000
BLIP_MODIFIER_FADE_IN | **Fade&nbsp;Effect**:&nbsp;<br>- DelayTimeMS: 0<br>- FadeTimeMS: 500<br>- FadeIn: Yes<br>- RemoveOnFadeOut: No
BLIP_MODIFIER_FADE_OUT_AND_DIE | **Conditional&nbsp;Removal**:&nbsp;<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_FADE_OUT_SLOW | **Fade&nbsp;Effect&nbsp;2**:&nbsp;<br>- FadeOutTimeMS: 5,000<br>- DoActionOnPop: Yes<br>- FadeInTimeMS: 150
BLIP_MODIFIER_FETCH_ESCAPING | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: Yes<br>- minAlpha: 0.5<br>- fadeRate: 0.04<br>- startDistance: 150
BLIP_MODIFIER_FISHING_SPOT_LEGENDARY | **Range**:&nbsp;<br>- PauseMap: Always<br>- Default: 50
BLIP_MODIFIER_FISHING_SPOT_NORMAL | **Range**:&nbsp;50
BLIP_MODIFIER_FLASH_FOREVER | **Flash&nbsp;Effect**:&nbsp;<br>- Count: -1
BLIP_MODIFIER_FOR_SALE | **Color**:&nbsp;`COLOR_RADAR_WRONG_TOD`<br>**Overlay&nbsp;Icon**:&nbsp;`BLIP_FOR_SALE`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_FORCE_GPS | **Show&nbsp;GPS&nbsp;Path**:&nbsp;<br>- Value: Yes<br>- TargetRangeDropOff: 15
BLIP_MODIFIER_FORCE_GPS_HORSE_ONLY | **Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `PlayerIsOnHorse`<br>- Value: `BLIP_MODIFIER_FORCE_GPS`<br>- StayTrueTimeMS: 50
BLIP_MODIFIER_FRIENDLY | **Color**:&nbsp;`COLOR_FRIENDLY`<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Label**:&nbsp;`BLIP_FRIEND`
BLIP_MODIFIER_FRIENDLY_OBJECTIVE | **Category**:&nbsp;`OBJECTIVE`<br>**Color**:&nbsp;`COLOR_OBJECTIVE`<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Label**:&nbsp;`BLIP_FRIEND`<br>**Scale**:&nbsp;<br>- Default: 1.1<br>- Edge: 0.9
BLIP_MODIFIER_GROUPING_ANNESBURG_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `ANNESBURG`
BLIP_MODIFIER_GROUPING_ANNESBURG_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `ANNESBURG`
BLIP_MODIFIER_GROUPING_ARMADILLO_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `ARMADILLO`
BLIP_MODIFIER_GROUPING_ARMADILLO_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `ARMADILLO`
BLIP_MODIFIER_GROUPING_BLACKWATER_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `BLACKWATER`
BLIP_MODIFIER_GROUPING_BLACKWATER_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `BLACKWATER`
BLIP_MODIFIER_GROUPING_CAMP_GROUP_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `CAMP`
BLIP_MODIFIER_GROUPING_CAMP_GROUP_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `CAMP`
BLIP_MODIFIER_GROUPING_EMERALD_RANCH_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `EMERALD_RANCH`
BLIP_MODIFIER_GROUPING_EMERALD_RANCH_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `EMERALD_RANCH`
BLIP_MODIFIER_GROUPING_LAGRAS_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `LAGRAS`
BLIP_MODIFIER_GROUPING_LAGRAS_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `LAGRAS`
BLIP_MODIFIER_GROUPING_RHODES_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `RHODES`
BLIP_MODIFIER_GROUPING_RHODES_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `RHODES`
BLIP_MODIFIER_GROUPING_SAINT_DENIS_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `SAINT_DENIS`
BLIP_MODIFIER_GROUPING_SAINT_DENIS_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `SAINT_DENIS`
BLIP_MODIFIER_GROUPING_STRAWBERRY_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `STRAWBERRY`
BLIP_MODIFIER_GROUPING_STRAWBERRY_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `STRAWBERRY`
BLIP_MODIFIER_GROUPING_TUMBLEWEED_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `TUMBLEWEED`
BLIP_MODIFIER_GROUPING_TUMBLEWEED_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `TUMBLEWEED`
BLIP_MODIFIER_GROUPING_VALENTINE_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `VALENTINE`
BLIP_MODIFIER_GROUPING_VALENTINE_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `VALENTINE`
BLIP_MODIFIER_GROUPING_VAN_HORN_FOLLOWER | **Grouping**:&nbsp;<br>- Leader: No<br>- Group: `VAN_HORN`
BLIP_MODIFIER_GROUPING_VAN_HORN_LEADER | **Grouping**:&nbsp;<br>- Leader: Yes<br>- Group: `VAN_HORN`
BLIP_MODIFIER_HERB_NORMAL | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: No<br>- minAlpha: 0.027<br>- fadeRate: 0.15<br>- startDistance: 20<br>**Range**:&nbsp;31
BLIP_MODIFIER_HERB_SHORT_RANGE | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: No<br>- minAlpha: 0.027<br>- fadeRate: 0.15<br>- startDistance: 8<br>**Range**:&nbsp;15
BLIP_MODIFIER_HERB_SURVIVALIST | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: No<br>- minAlpha: 0.027<br>- fadeRate: 0.15<br>- startDistance: 60<br>**Range**:&nbsp;75
BLIP_MODIFIER_HIDDEN | **Visible&nbsp;On**:&nbsp;Yes
BLIP_MODIFIER_HIDE_HEIGHT_MARKER | **Height&nbsp;Indicator**:&nbsp;No
BLIP_MODIFIER_HIDEOUT_ABANDONED | **Color**:&nbsp;`COLOR_RADAR_WRONG_TOD`<br>**Overlay&nbsp;Icon**:&nbsp;`BLIP_TIME_OF_DAY`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_HIGH_CATEGORY | **Category**:&nbsp;`MISSION_ACTIVE`
BLIP_MODIFIER_HORSE_REVIVE | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_HORSE_REVIVE`<br>**Overlay Color:** `COLOR_RED`<br>**Pulse**:&nbsp;<br>- Count: 4
BLIP_MODIFIER_HORSE_REVIVE_2 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_HORSE_REVIVE`<br>**Overlay Color:** `COLOR_RED`<br>**Pulse&nbsp;(Alpha)**:&nbsp;<br>- DurationMS: 2,500<br>- Count: -1<br>- FadeInOut: Yes
BLIP_MODIFIER_HORSE_REVIVE_3 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_HORSE_REVIVE`<br>**Overlay Color:** `COLOR_RED`<br>**Pulse&nbsp;(Alpha)**:&nbsp;<br>- DurationMS: 1,000<br>- Count: -1<br>- FadeInOut: Yes
BLIP_MODIFIER_HORSE_REVIVE_4 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_HORSE_REVIVE`<br>**Overlay Color:** `COLOR_RED`<br>**Pulse&nbsp;(Alpha)**:&nbsp;<br>- DurationMS: 500<br>- Count: -1<br>- FadeInOut: Yes
BLIP_MODIFIER_HORSE_STOLEN | **Color**:&nbsp;`COLOR_ENEMY`
BLIP_MODIFIER_JOB | **Overlay&nbsp;Icon**:&nbsp;`BLIP_JOB`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_BILL | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_BILL`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_CHARLES | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_CHARLES`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_HOSEA | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_HOSEA`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_JAVIER | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_JAVIER`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_JOHN | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_JOHN`<br>**Overlay Color:** `COLOR_OBJECTIVE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_KAREN | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_KAREN`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_KIERAN | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_KIERAN`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_LENNY | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_LENNY`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_LOANSHARK | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_LOANSHARK`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_MICAH | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_MICAH`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_PEARSON | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_PEARSON`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_SEAN | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_SEAN`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_STRAUSS | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_STRAUSS`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_TILLY | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_TILLY`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_JOB_UNCLE | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_UNCLE`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_KEY_JOB | **Overlay&nbsp;Icon**:&nbsp;`BLIP_JOB`<br>**Overlay Color:** `COLOR_OBJECTIVE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_KEY_MISSION | **Color**:&nbsp;`COLOR_OBJECTIVE`
BLIP_MODIFIER_KEY_MISSION_OBJECT | **Color**:&nbsp;`COLOR_OBJECTIVE`<br>**Inverted&nbsp;State**:&nbsp;No
BLIP_MODIFIER_LAW_ORDER | **Conditional&nbsp;Style&nbsp;List**:&nbsp;<br>- ConditionData: `CopCriminalKnown`<br>- OnTrue: `{"Push":["AUTO_MODIFIER_COP_CRIMINAL_KNOWN"],"Pop":["AUTO_MODIFIER_COP_CRIMINAL_UNKNOWN"]}`<br>- OnFalse: `{"Push":["AUTO_MODIFIER_COP_CRIMINAL_UNKNOWN"],"Pop":["AUTO_MODIFIER_COP_CRIMINAL_KNOWN"]}`<br>**Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `CopWhereaboutsUnknown`<br>- Value: `AUTO_MODIFIER_COP_SEARCH_CONE`<br>**Range**:&nbsp;<br>- PauseMap: 300<br>- Default: Zoom Level<br>**Threat&nbsp;Indicator**:&nbsp;<br>- MaxThreatDistance: 200
BLIP_MODIFIER_LEGENDARY | **Color**:&nbsp;`COLOR_YELLOWLIGHT`<br>**Range**:&nbsp;<br>- PauseMap: Always<br>- Default: 150
BLIP_MODIFIER_LOCAL_PLAYER_FOLLOWING_OBJECTIVE | **Color**:&nbsp;`COLOR_OBJECTIVE`
BLIP_MODIFIER_LOCAL_PLAYER_MADE_VISIBLE | **Flash&nbsp;Effect**:&nbsp;<br>- Count: -1
BLIP_MODIFIER_LOCAL_PLAYER_OWNED | **Color**:&nbsp;`COLOR_LOCAL_PLAYER`
BLIP_MODIFIER_LOCKED | **Color**:&nbsp;`COLOR_LOW_PRIORITY`<br>**Overlay&nbsp;Icon**:&nbsp;`BLIP_LOCKED`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9<br>**Transparency**:&nbsp;<br>- Value: 0.1<br>- LayerFlags: `AreaLayer`
BLIP_MODIFIER_LOOTED | **Transparency**:&nbsp;0.65
BLIP_MODIFIER_LOS_DISAPPEARING | **Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `PedInLOS`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_MC_STEALTH_LENIENT | **Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `MCStealth_Lenient`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_MC_STEALTH_MEDIUM | **Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `MCStealth_Medium`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 150
BLIP_MODIFIER_MC_STEALTH_STRICT | **Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `MCStealth_Strict`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_MC_STEALTH_VERY_LENIENT | **Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `MCStealth_VeryLenient`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_MC_STEALTH_VERY_STRICT | **Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `MCStealth_VeryStrict`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_MISSION_UNAVAILABLE | **Color**:&nbsp;`COLOR_RADAR_WRONG_TOD`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_MP_COLOR_1 | **Color**:&nbsp;`COLOR_NET_PLAYER1`
BLIP_MODIFIER_MP_COLOR_2 | **Color**:&nbsp;`COLOR_NET_PLAYER2`
BLIP_MODIFIER_MP_COLOR_3 | **Color**:&nbsp;`COLOR_NET_PLAYER3`
BLIP_MODIFIER_MP_COLOR_4 | **Color**:&nbsp;`COLOR_NET_PLAYER4`
BLIP_MODIFIER_MP_COLOR_5 | **Color**:&nbsp;`COLOR_NET_PLAYER5`
BLIP_MODIFIER_MP_COLOR_6 | **Color**:&nbsp;`COLOR_NET_PLAYER6`
BLIP_MODIFIER_MP_COLOR_7 | **Color**:&nbsp;`COLOR_NET_PLAYER7`
BLIP_MODIFIER_MP_COLOR_8 | **Color**:&nbsp;`COLOR_NET_PLAYER8`
BLIP_MODIFIER_MP_COLOR_9 | **Color**:&nbsp;`COLOR_NET_PLAYER9`
BLIP_MODIFIER_MP_COLOR_10 | **Color**:&nbsp;`COLOR_NET_PLAYER10`
BLIP_MODIFIER_MP_COLOR_11 | **Color**:&nbsp;`COLOR_NET_PLAYER11`
BLIP_MODIFIER_MP_COLOR_12 | **Color**:&nbsp;`COLOR_NET_PLAYER12`
BLIP_MODIFIER_MP_COLOR_13 | **Color**:&nbsp;`COLOR_NET_PLAYER13`
BLIP_MODIFIER_MP_COLOR_14 | **Color**:&nbsp;`COLOR_NET_PLAYER14`
BLIP_MODIFIER_MP_COLOR_15 | **Color**:&nbsp;`COLOR_NET_PLAYER15`
BLIP_MODIFIER_MP_COLOR_16 | **Color**:&nbsp;`COLOR_NET_PLAYER16`
BLIP_MODIFIER_MP_COLOR_17 | **Color**:&nbsp;`COLOR_NET_PLAYER17`
BLIP_MODIFIER_MP_COLOR_18 | **Color**:&nbsp;`COLOR_NET_PLAYER18`
BLIP_MODIFIER_MP_COLOR_19 | **Color**:&nbsp;`COLOR_NET_PLAYER19`
BLIP_MODIFIER_MP_COLOR_20 | **Color**:&nbsp;`COLOR_NET_PLAYER20`
BLIP_MODIFIER_MP_COLOR_21 | **Color**:&nbsp;`COLOR_NET_PLAYER21`
BLIP_MODIFIER_MP_COLOR_22 | **Color**:&nbsp;`COLOR_NET_PLAYER22`
BLIP_MODIFIER_MP_COLOR_23 | **Color**:&nbsp;`COLOR_NET_PLAYER23`
BLIP_MODIFIER_MP_COLOR_24 | **Color**:&nbsp;`COLOR_NET_PLAYER24`
BLIP_MODIFIER_MP_COLOR_25 | **Color**:&nbsp;`COLOR_NET_PLAYER25`
BLIP_MODIFIER_MP_COLOR_26 | **Color**:&nbsp;`COLOR_NET_PLAYER26`
BLIP_MODIFIER_MP_COLOR_27 | **Color**:&nbsp;`COLOR_NET_PLAYER27`
BLIP_MODIFIER_MP_COLOR_28 | **Color**:&nbsp;`COLOR_NET_PLAYER28`
BLIP_MODIFIER_MP_COLOR_29 | **Color**:&nbsp;`COLOR_NET_PLAYER29`
BLIP_MODIFIER_MP_COLOR_30 | **Color**:&nbsp;`COLOR_NET_PLAYER30`
BLIP_MODIFIER_MP_COLOR_31 | **Color**:&nbsp;`COLOR_NET_PLAYER31`
BLIP_MODIFIER_MP_COLOR_32 | **Color**:&nbsp;`COLOR_NET_PLAYER32`
BLIP_MODIFIER_MP_DOWNED | **Category**:&nbsp;`MISSION_ACTIVE`<br>**Icon**:&nbsp;`BLIP_AMBIENT_PED_DOWNED`<br>**Range**:&nbsp;Zoom Level<br>**Scale**:&nbsp;1.2
BLIP_MODIFIER_MP_ENEMY_HOLDING | **Color**:&nbsp;`COLOR_ENEMY`
BLIP_MODIFIER_MP_FRIENDLY_HOLDING | **Color**:&nbsp;`COLOR_NET_PLAYER1`
BLIP_MODIFIER_MP_HOT_BLIP | **Color**:&nbsp;`COLOR_ORANGE`<br>**Range**:&nbsp;Always
BLIP_MODIFIER_MP_HUNTER | **Icon**:&nbsp;`BLIP_AMBIENT_HUNTER`
BLIP_MODIFIER_MP_JOB_PLAYER_FADE | **Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `MP_DM_Blip_Enemy`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_MP_NEUTRAL | **Color**:&nbsp;`COLOR_MP_OBJECTIVE_NEUTRAL`
BLIP_MODIFIER_MP_OBJECTIVE | **Category**:&nbsp;`OBJECTIVE`<br>**Color**:&nbsp;`COLOR_MP_OBJECTIVE`<br>**Range**:&nbsp;Always
BLIP_MODIFIER_MP_OBJECTIVE_ENEMY | **Category**:&nbsp;`OBJECTIVE`<br>**Color**:&nbsp;`COLOR_MP_OBJECTIVE_ENEMY`<br>**Range**:&nbsp;Always
BLIP_MODIFIER_MP_OBJECTIVE_FRIENDLY | **Category**:&nbsp;`VIP`<br>**Color**:&nbsp;`COLOR_MP_OBJECTIVE_FRIENDLY`<br>**Range**:&nbsp;Always
BLIP_MODIFIER_MP_OBJECTIVE_NEUTRAL | **Category**:&nbsp;`OBJECTIVE`<br>**Color**:&nbsp;`COLOR_MP_OBJECTIVE_NEUTRAL`<br>**Range**:&nbsp;Always
BLIP_MODIFIER_MP_PLAYER_ALLY | **Color**:&nbsp;`COLOR_NET_PLAYER1`
BLIP_MODIFIER_MP_PLAYER_ALLY_WOUNDED | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_REVIVE`<br>**Overlay Color:** `COLOR_WHITE`
BLIP_MODIFIER_MP_PLAYER_CONTROL | **Category**:&nbsp;`OBJECTIVE`<br>**Pulse**:&nbsp;<br>- Count: 4<br>**Scale**:&nbsp;1.2
BLIP_MODIFIER_MP_PLAYER_COOP | **Color**:&nbsp;`COLOR_CO_OP_PLAYER`
BLIP_MODIFIER_MP_PLAYER_DISAPPEARING | **Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `AIBlips`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_MP_PLAYER_ENEMY | **Color**:&nbsp;`COLOR_ENEMY`<br>**Range**:&nbsp;Zoom Level<br>**Threat&nbsp;Indicator**:&nbsp;<br>- MaxThreatDistance: 200
BLIP_MODIFIER_MP_PLAYER_LOS_ONLY | **Fade&nbsp;Condition**:&nbsp;<br>- ConditionData: `PedInLOS`<br>- FadeInTimeMS: 150<br>- StayTrueTimeMS: 2,000<br>- FadeOutTimeMS: 1,500
BLIP_MODIFIER_MP_PLAYER_NEUTRAL | **Color**:&nbsp;`COLOR_LOW_PRIORITY`
BLIP_MODIFIER_MP_PLAYER_UNAVAILABLE | **Transparency**:&nbsp;0.5
BLIP_MODIFIER_MP_PLAYER_WINNING | **Color**:&nbsp;`COLOR_WINNING_PLAYER`
BLIP_MODIFIER_MP_PLAYER_WITH_BOUNTY | **Color**:&nbsp;`COLOR_ENEMY`<br>**Icon**:&nbsp;`BLIP_AMBIENT_BOUNTY_TARGET`
BLIP_MODIFIER_MP_REVIVE | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_REVIVE`<br>**Overlay Color:** `COLOR_WHITE`
BLIP_MODIFIER_MP_RIVAL_RACER | **Color**:&nbsp;`COLOR_ENEMY`
BLIP_MODIFIER_MP_TEAM_COLOR_1 | **Color**:&nbsp;`COLOR_NET_PLAYER3`
BLIP_MODIFIER_MP_TEAM_COLOR_2 | **Color**:&nbsp;`COLOR_NET_PLAYER4`
BLIP_MODIFIER_MP_TEAM_COLOR_3 | **Color**:&nbsp;`COLOR_NET_PLAYER5`
BLIP_MODIFIER_MP_TEAM_COLOR_4 | **Color**:&nbsp;`COLOR_NET_PLAYER6`
BLIP_MODIFIER_MP_TEAM_COLOR_5 | **Color**:&nbsp;`COLOR_NET_PLAYER7`
BLIP_MODIFIER_MP_TEAM_COLOR_6 | **Color**:&nbsp;`COLOR_NET_PLAYER8`
BLIP_MODIFIER_MP_TEAM_COLOR_7 | **Color**:&nbsp;`COLOR_NET_PLAYER9`
BLIP_MODIFIER_MP_TEAM_COLOR_8 | **Color**:&nbsp;`COLOR_NET_PLAYER10`
BLIP_MODIFIER_MP_WHITE_FLAG | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_FLAG`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_NEUTRAL_ON_GUARD | **Category**:&nbsp;`OBJECTIVE`<br>**Color**:&nbsp;`COLOR_OBJECTIVE`<br>**Heading&nbsp;Type**:&nbsp;Cone<br>**Heading Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;1.1
BLIP_MODIFIER_OBJECTIVE | **Category**:&nbsp;`MISSION_ACTIVE`<br>**Color**:&nbsp;`COLOR_OBJECTIVE`<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Range**:&nbsp;Always<br>**Show&nbsp;GPS&nbsp;Path**:&nbsp;No
BLIP_MODIFIER_OBJECTIVE_GET_CLOSE |
BLIP_MODIFIER_OPEN_RACE_CHECKPOINT | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: Yes<br>- minAlpha: 0.5<br>- fadeRate: 0.005<br>- startDistance: 100
BLIP_MODIFIER_OUTSIDE_TOD | **Color**:&nbsp;`COLOR_RADAR_WRONG_TOD`<br>**Overlay&nbsp;Icon**:&nbsp;`BLIP_TIME_OF_DAY`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_1 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_1`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_2 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_2`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_3 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_3`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_4 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_4`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_5 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_5`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_1 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER1`
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_2 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER2`
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_3 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER3`
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_4 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER4`
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_5 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER5`
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_6 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER6`
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_7 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER7`
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_8 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER8`
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_9 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER9`
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_10 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_RING`<br>**Overlay Color:** `COLOR_NET_PLAYER10`
BLIP_MODIFIER_OVERLAY_SADDLE | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_SADDLE`<br>**Overlay Color:** `COLOR_WHITE`
BLIP_MODIFIER_OVERLAY_SADDLE_STOLEN | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_SADDLE`<br>**Overlay Color:** `COLOR_ENEMY`
BLIP_MODIFIER_OVERLAY_WHITE_1 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_WHITE_1`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_WHITE_2 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_WHITE_2`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_WHITE_3 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_WHITE_3`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_WHITE_4 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_WHITE_4`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_OVERLAY_WHITE_5 | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_WHITE_5`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_PARTY | **Overlay&nbsp;Icon**:&nbsp;`BLIP_OVERLAY_PARTY`<br>**Overlay Color:** `COLOR_WHITE`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_PICKUP_NEW | **Overlay&nbsp;Icon**:&nbsp;`BLIP_AMBIENT_NEW`<br>**Overlay Color:** `COLOR_WHITE`
BLIP_MODIFIER_PICKUP_SURVIVAL_MODES | **Range**:&nbsp;50
BLIP_MODIFIER_PICKUP_UNAVAILABLE | **Transparency**:&nbsp;0.5
BLIP_MODIFIER_PICKUP_WEAPON_LEGENDARY | **Category**:&nbsp;`PICKUPS`<br>**Color**:&nbsp;`COLOR_YELLOWLIGHT`
BLIP_MODIFIER_PICKUP_WEAPON_NEW | **Category**:&nbsp;`PICKUPS`<br>**Color**:&nbsp;`COLOR_WHITE`<br>**Height&nbsp;Indicator**:&nbsp;Yes<br>**Icon**:&nbsp;`BLIP_WEAPON`<br>**Label**:&nbsp;`BLIP_WEAPON`<br>**Range**:&nbsp;<br>- PauseMap: Zoom Level<br>- Default: Zoom Level<br>**Scale**:&nbsp;1
BLIP_MODIFIER_PICKUP_WEAPON_OF_CHOICE | **Color**:&nbsp;`COLOR_OBJECTIVE`
BLIP_MODIFIER_PICKUP_WEAPON_OWNED | **Category**:&nbsp;`PICKUPS`<br>**Color**:&nbsp;`COLOR_WHITE`
BLIP_MODIFIER_PICKUP_WEAPON_RARE | **Category**:&nbsp;`PICKUPS`<br>**Color**:&nbsp;`COLOR_BLUE`
BLIP_MODIFIER_PLAYER_HORSE_HITCHED | **Icon**:&nbsp;`BLIP_HORSE_OWNED_HITCHED`
BLIP_MODIFIER_PLAYER_HORSE_IN_RANGE | **Color**:&nbsp;`COLOR_WHITE`
BLIP_MODIFIER_PLAYER_HORSE_IN_RANGE_WHISTLE | **Pulse**:&nbsp;<br>- Count: 4
BLIP_MODIFIER_PLAYER_HORSE_INACTIVE | **Color**:&nbsp;`COLOR_LOW_PRIORITY`
BLIP_MODIFIER_PLAYER_HORSE_OUT_OF_RANGE | **Color**:&nbsp;`COLOR_LOW_PRIORITY`
BLIP_MODIFIER_PLAYER_HORSE_OUT_OF_RANGE_WHISTLE | **Flash&nbsp;Effect**:&nbsp;<br>- Count: 4
BLIP_MODIFIER_POSSE_ALLY | **Category**:&nbsp;`OTHER_PLAYER_FRIENDLY`<br>**Color**:&nbsp;`COLOR_POSSE_ALLY`<br>**Range**:&nbsp;Always<br>**Transparency**:&nbsp;1
BLIP_MODIFIER_POSSE_ALLY_OWNED | **Color**:&nbsp;`COLOR_POSSE_ALLY`
BLIP_MODIFIER_POSSE_ENEMY | **Category**:&nbsp;`ENEMY`<br>**Color**:&nbsp;`COLOR_POSSE_ENEMY`<br>**Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: Yes<br>- minAlpha: 0.001<br>- fadeRate: 0.005<br>- startDistance: 350<br>**Range**:&nbsp;Zoom Level<br>**Threat&nbsp;Indicator**:&nbsp;<br>- MaxThreatDistance: 200
BLIP_MODIFIER_POSSE_ENEMY_OWNED | **Color**:&nbsp;`COLOR_POSSE_ENEMY`
BLIP_MODIFIER_POSSE_NEUTRAL | **Category**:&nbsp;`OTHER_PLAYER`<br>**Color**:&nbsp;`COLOR_POSSE_NEUTRAL`<br>**Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: Yes<br>- minAlpha: 0.001<br>- fadeRate: 0.005<br>- startDistance: 350
BLIP_MODIFIER_POSSE_NEUTRAL_OWNED | **Color**:&nbsp;`COLOR_POSSE_NEUTRAL`
BLIP_MODIFIER_PULSE_FOREVER | **Pulse**:&nbsp;<br>- Count: -1
BLIP_MODIFIER_RACE_CHECKPOINT_ALT | **Color**:&nbsp;`COLOR_ORANGE`
BLIP_MODIFIER_RADAR_EDGE_ALWAYS | **Range**:&nbsp;Always
BLIP_MODIFIER_RADAR_EDGE_NEVER | **Range**:&nbsp;Zoom Level
BLIP_MODIFIER_SCALE_1 | **Scale**:&nbsp;1.2
BLIP_MODIFIER_SCALE_2 | **Scale**:&nbsp;1.5
BLIP_MODIFIER_SHOP_UNAVAILABLE | **Color**:&nbsp;`COLOR_RADAR_WRONG_TOD`
BLIP_MODIFIER_SHOW_HEIGHT | **Height&nbsp;Indicator**:&nbsp;Yes
BLIP_MODIFIER_SHRINK_WARNING_1 | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- Count: -1<br>- FadeInOut: No<br>- DurationMS: 1,000
BLIP_MODIFIER_SHRINK_WARNING_2 | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- Count: -1<br>- FadeInOut: No<br>- DurationMS: 500
BLIP_MODIFIER_SP_DOWNED | **Category**:&nbsp;`LOOT`<br>**Color**:&nbsp;`COLOR_BLACK`<br>**Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `HideBlipForCarrying`<br>- Value: `BLIP_MODIFIER_HIDDEN`<br>**Icon**:&nbsp;`BLIP_AMBIENT_CORPSE`<br>**Range**:&nbsp;Zoom Level<br>**Scale**:&nbsp;1
BLIP_MODIFIER_TEMP_HORSE_HITCHED | **Icon**:&nbsp;`BLIP_HORSE_TEMP_HITCHED`
BLIP_MODIFIER_TEST_GPS_MODULE | **Show&nbsp;GPS&nbsp;Path**:&nbsp;<br>- Value: Yes<br>- GpsFlags: `GPS_FLAG_IGNORE_ONE_WAY GPS_FLAG_CUSTOM_PROXIMITY`
BLIP_MODIFIER_TEXT_ONLY | **Color**:&nbsp;`COLOR_GREY`<br>**Icon**:&nbsp;`BLIP_CODE_LEVEL`<br>**Scale**:&nbsp;1<br>**Visible&nbsp;On**:&nbsp;<br>- Filter: `{"Value":["Embedded"]}`
BLIP_MODIFIER_TOD_DAYTIME_ONLY | **Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `MG_EveningNight`<br>- Value: `BLIP_MODIFIER_OUTSIDE_TOD`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_TOD_NIGHTTIME_ONLY | **Conditional&nbsp;Style&nbsp;Toggle**:&nbsp;<br>- ConditionData: `MG_MorningAfternoon`<br>- Value: `BLIP_MODIFIER_OUTSIDE_TOD`<br>**Scale**:&nbsp;<br>- Default: 1<br>- Edge: 0.9<br>- Embedded: 0.9
BLIP_MODIFIER_TOWN_POSSE_MEMBER | **Range**:&nbsp;Zoom Level
BLIP_MODIFIER_TRACKING | **Tracking**:&nbsp;<br>- SpawnInterval: 1,500<br>- StyleKey: `BLIP_STYLE_TRACKING_DOT`
BLIP_MODIFIER_TRAIN_MISSION | **Range**:&nbsp;Always
BLIP_MODIFIER_UNDISCOVERED | **Color**:&nbsp;`COLOR_RADAR_UNDISCOVERED`
BLIP_MODIFIER_URGENT | **Pulse**:&nbsp;<br>- Count: -1
BLIP_MODIFIER_URGENT_ALERT | **Pulse**:&nbsp;<br>- Count: 10<br>**Range**:&nbsp;Always
BLIP_MODIFIER_VERYHIGH_CATEGORY | **Category**:&nbsp;`VIP`
BLIP_MODIFIER_WANTED_PULSE_1 | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- Count: -1<br>- FadeInOut: No<br>- DurationMS: 2,500<br>- MinAlpha: 0.5<br>- MaxAlpha: 1
BLIP_MODIFIER_WANTED_PULSE_2 | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- Count: -1<br>- FadeInOut: No<br>- DurationMS: 2,000<br>- MinAlpha: 0.5<br>- MaxAlpha: 1
BLIP_MODIFIER_WANTED_PULSE_3 | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- Count: -1<br>- FadeInOut: No<br>- DurationMS: 1,500<br>- MinAlpha: 0.5<br>- MaxAlpha: 1
BLIP_MODIFIER_WANTED_PULSE_4 | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- Count: -1<br>- FadeInOut: No<br>- DurationMS: 1,000<br>- MinAlpha: 0.5<br>- MaxAlpha: 1
BLIP_MODIFIER_WANTED_PULSE_5 | **Pulse&nbsp;(Alpha)**:&nbsp;<br>- Count: -1<br>- FadeInOut: No<br>- DurationMS: 500<br>- MinAlpha: 0.5<br>- MaxAlpha: 1
BLIP_MODIFIER_WILDERNESS_CHEST_LONG | **Fade&nbsp;by&nbsp;Distance**:&nbsp;<br>- edgeOnly: No<br>- minAlpha: 0.027<br>- fadeRate: 0.15<br>- startDistance: 20<br>**Range**:&nbsp;30
BLIP_MODIFIER_WITNESS_IDENTIFIED | **Color**:&nbsp;`COLOR_WITNESS_IDENTIFIED`
BLIP_MODIFIER_WITNESS_INVESTIGATING | **Color**:&nbsp;`COLOR_WITNESS_INVESTIGATING`<br>**Pulse**:&nbsp;<br>- Count: 4
BLIP_MODIFIER_WITNESS_UNIDENTIFIED | **Color**:&nbsp;`COLOR_WITNESS_UNIDENTIFIED`

## Examples

Hashname | Examples
------------ | ----------------
BLIP_MODIFIER_ANIMAL_SKINNED<br>BLIP_MODIFIER_AREA<br>BLIP_MODIFIER_AREA_ACCURATE<br>BLIP_MODIFIER_AREA_CLAMPED_PULSE<br>BLIP_MODIFIER_AREA_CONTESTED<br>BLIP_MODIFIER_AREA_DIRECTIONAL<br>BLIP_MODIFIER_AREA_HIDE_ON_INSIDE<br>BLIP_MODIFIER_AREA_HIDE_ON_OUTSIDE<br>BLIP_MODIFIER_AREA_NO_BLIP<br>BLIP_MODIFIER_AREA_OUT_OF_BOUNDS | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_001.jpeg)
BLIP_MODIFIER_AREA_PULSE<br>BLIP_MODIFIER_AREA_TAKEOVER<br>BLIP_MODIFIER_ATTENTION<br>BLIP_MODIFIER_BOUNTY_TARGET_INCAPACITATED<br>BLIP_MODIFIER_CAMP_NOT_READY<br>BLIP_MODIFIER_CHASE<br>BLIP_MODIFIER_COLLECTIBLE_FULL<br>BLIP_MODIFIER_COMPANION_ACTIVITY<br>BLIP_MODIFIER_COMPANION_CONVERSATION<br>BLIP_MODIFIER_COMPANION_DOG | ![screen_2.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_002.jpeg)
BLIP_MODIFIER_COMPANION_OBJECTIVE<br>BLIP_MODIFIER_COMPANION_WOUNDED<br>BLIP_MODIFIER_COMPASS_OBJECTIVE<br>BLIP_MODIFIER_CREATOR_FOCUS<br>BLIP_MODIFIER_CULL_ON_DEATH<br>BLIP_MODIFIER_DEBUG_BLUE<br>BLIP_MODIFIER_DEBUG_GREEN<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_50<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_60<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_70 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_003.jpeg)
BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_80<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_90<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_100<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_110<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_120<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_130<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_140<br>BLIP_MODIFIER_DEBUG_MP_PLAYER_RANGE_150<br>BLIP_MODIFIER_DEBUG_PINK<br>BLIP_MODIFIER_DEBUG_RED | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_004.jpeg)
BLIP_MODIFIER_DEBUG_YELLOW<br>BLIP_MODIFIER_DIRECTION_ONLY<br>BLIP_MODIFIER_DISTANCE_FADE_LONG<br>BLIP_MODIFIER_DISTANCE_FADE_MEDIUM<br>BLIP_MODIFIER_DISTANCE_FADE_SHORT<br>BLIP_MODIFIER_EAGLE_EYE<br>BLIP_MODIFIER_ENEMY<br>BLIP_MODIFIER_ENEMY_AQUATIC<br>BLIP_MODIFIER_ENEMY_CONFRONTING<br>BLIP_MODIFIER_ENEMY_DISAPPEARING | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_005.jpeg)
BLIP_MODIFIER_ENEMY_DISAPPEARING_NO_FLEE_CHECKS<br>BLIP_MODIFIER_ENEMY_DISAPPEARING_NO_SCREEN_CHECKS<br>BLIP_MODIFIER_ENEMY_FLEEING<br>BLIP_MODIFIER_ENEMY_GUNSHOTS_FADE_ON_START<br>BLIP_MODIFIER_ENEMY_GUNSHOTS_ONLY<br>BLIP_MODIFIER_ENEMY_GUNSHOTS_ONLY_DONT_SHOW_LAST<br>BLIP_MODIFIER_ENEMY_IMPORTANT<br>BLIP_MODIFIER_ENEMY_IS_ALERTED<br>BLIP_MODIFIER_ENEMY_LOWER_AWARENESS<br>BLIP_MODIFIER_ENEMY_MUST_AGGRO | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_006.jpeg)
BLIP_MODIFIER_ENEMY_OBJECTIVE<br>BLIP_MODIFIER_ENEMY_ON_GUARD<br>BLIP_MODIFIER_ENEMY_ON_GUARD_DISAPPEARING<br>BLIP_MODIFIER_ENEMY_ON_GUARD_NO_CONE<br>BLIP_MODIFIER_ENEMY_STEALTH_KILL<br>BLIP_MODIFIER_ENEMY_TARGETED_ONLY<br>BLIP_MODIFIER_FADE<br>BLIP_MODIFIER_FADE_IN<br>BLIP_MODIFIER_FADE_OUT_AND_DIE<br>BLIP_MODIFIER_FADE_OUT_SLOW | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_007.jpeg)
BLIP_MODIFIER_FETCH_ESCAPING<br>BLIP_MODIFIER_FETCH_VIP<br>BLIP_MODIFIER_FISHING_SPOT_LEGENDARY<br>BLIP_MODIFIER_FISHING_SPOT_NORMAL<br>BLIP_MODIFIER_FLASH_FOREVER<br>BLIP_MODIFIER_FLASH_LONG<br>BLIP_MODIFIER_FLASH_MEDIUM<br>BLIP_MODIFIER_FLASH_SHORT<br>BLIP_MODIFIER_FORCE_GPS<br>BLIP_MODIFIER_FORCE_GPS_HORSE_ONLY | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_008.jpeg)
BLIP_MODIFIER_FOR_SALE<br>BLIP_MODIFIER_FRIENDLY<br>BLIP_MODIFIER_FRIENDLY_OBJECTIVE<br>BLIP_MODIFIER_GROUPING_ANNESBURG_FOLLOWER<br>BLIP_MODIFIER_GROUPING_ANNESBURG_LEADER<br>BLIP_MODIFIER_GROUPING_ARMADILLO_FOLLOWER<br>BLIP_MODIFIER_GROUPING_ARMADILLO_LEADER<br>BLIP_MODIFIER_GROUPING_BLACKWATER_FOLLOWER<br>BLIP_MODIFIER_GROUPING_BLACKWATER_LEADER<br>BLIP_MODIFIER_GROUPING_CAMP_GROUP_FOLLOWER | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_009.jpeg)
BLIP_MODIFIER_GROUPING_CAMP_GROUP_LEADER<br>BLIP_MODIFIER_GROUPING_EMERALD_RANCH_FOLLOWER<br>BLIP_MODIFIER_GROUPING_EMERALD_RANCH_LEADER<br>BLIP_MODIFIER_GROUPING_LAGRAS_FOLLOWER<br>BLIP_MODIFIER_GROUPING_LAGRAS_LEADER<br>BLIP_MODIFIER_GROUPING_RHODES_FOLLOWER<br>BLIP_MODIFIER_GROUPING_RHODES_LEADER<br>BLIP_MODIFIER_GROUPING_SAINT_DENIS_FOLLOWER<br>BLIP_MODIFIER_GROUPING_SAINT_DENIS_LEADER<br>BLIP_MODIFIER_GROUPING_STRAWBERRY_FOLLOWER | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_010.jpeg)
BLIP_MODIFIER_GROUPING_STRAWBERRY_LEADER<br>BLIP_MODIFIER_GROUPING_THIEVES_LANDING_FOLLOWER<br>BLIP_MODIFIER_GROUPING_THIEVES_LANDING_LEADER<br>BLIP_MODIFIER_GROUPING_TUMBLEWEED_FOLLOWER<br>BLIP_MODIFIER_GROUPING_TUMBLEWEED_LEADER<br>BLIP_MODIFIER_GROUPING_VALENTINE_FOLLOWER<br>BLIP_MODIFIER_GROUPING_VALENTINE_LEADER<br>BLIP_MODIFIER_GROUPING_VAN_HORN_FOLLOWER<br>BLIP_MODIFIER_GROUPING_VAN_HORN_LEADER<br>BLIP_MODIFIER_HERB_NORMAL | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_011.jpeg)
BLIP_MODIFIER_HERB_SHORT_RANGE<br>BLIP_MODIFIER_HERB_SURVIVALIST<br>BLIP_MODIFIER_HIDDEN<br>BLIP_MODIFIER_HIDEOUT_ABANDONED<br>BLIP_MODIFIER_HIDE_HEIGHT_MARKER<br>BLIP_MODIFIER_HIGH_CATEGORY<br>BLIP_MODIFIER_HORSE_REVIVE<br>BLIP_MODIFIER_HORSE_REVIVE_2<br>BLIP_MODIFIER_HORSE_REVIVE_3<br>BLIP_MODIFIER_HORSE_REVIVE_4 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_012.jpeg)
BLIP_MODIFIER_HORSE_STOLEN<br>BLIP_MODIFIER_HOSTILITY_COLOR_1<br>BLIP_MODIFIER_HOSTILITY_COLOR_2<br>BLIP_MODIFIER_HOSTILITY_COLOR_3<br>BLIP_MODIFIER_HOSTILITY_VISIBILITY_1<br>BLIP_MODIFIER_HOSTILITY_VISIBILITY_2<br>BLIP_MODIFIER_HOSTILITY_VISIBILITY_3<br>BLIP_MODIFIER_HOSTILITY_VISIBILITY_4<br>BLIP_MODIFIER_JOB<br>BLIP_MODIFIER_JOB_BILL | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_013.jpeg)
BLIP_MODIFIER_JOB_CHARLES<br>BLIP_MODIFIER_JOB_HOSEA<br>BLIP_MODIFIER_JOB_JAVIER<br>BLIP_MODIFIER_JOB_JOHN<br>BLIP_MODIFIER_JOB_KAREN<br>BLIP_MODIFIER_JOB_KIERAN<br>BLIP_MODIFIER_JOB_LENNY<br>BLIP_MODIFIER_JOB_LOANSHARK<br>BLIP_MODIFIER_JOB_MICAH<br>BLIP_MODIFIER_JOB_PEARSON | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_014.jpeg)
BLIP_MODIFIER_JOB_SEAN<br>BLIP_MODIFIER_JOB_STRAUSS<br>BLIP_MODIFIER_JOB_TILLY<br>BLIP_MODIFIER_JOB_UNCLE<br>BLIP_MODIFIER_KEY_JOB<br>BLIP_MODIFIER_KEY_MISSION<br>BLIP_MODIFIER_KEY_MISSION_OBJECT<br>BLIP_MODIFIER_LAW_ORDER<br>BLIP_MODIFIER_LEGENDARY<br>BLIP_MODIFIER_LOCAL_PLAYER_FOLLOWING_OBJECTIVE | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_015.jpeg)
BLIP_MODIFIER_LOCAL_PLAYER_HOSTILITY_HIGH<br>BLIP_MODIFIER_LOCAL_PLAYER_HOSTILITY_MEDIUM<br>BLIP_MODIFIER_LOCAL_PLAYER_MADE_VISIBLE<br>BLIP_MODIFIER_LOCAL_PLAYER_OWNED<br>BLIP_MODIFIER_LOCKED<br>BLIP_MODIFIER_LOOTED<br>BLIP_MODIFIER_LOS_DISAPPEARING<br>BLIP_MODIFIER_MC_STEALTH_LENIENT<br>BLIP_MODIFIER_MC_STEALTH_MEDIUM<br>BLIP_MODIFIER_MC_STEALTH_STRICT | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_016.jpeg)
BLIP_MODIFIER_MC_STEALTH_VERY_LENIENT<br>BLIP_MODIFIER_MC_STEALTH_VERY_STRICT<br>BLIP_MODIFIER_MISSION_UNAVAILABLE<br>BLIP_MODIFIER_MP_COLOR_1<br>BLIP_MODIFIER_MP_COLOR_2<br>BLIP_MODIFIER_MP_COLOR_3<br>BLIP_MODIFIER_MP_COLOR_4<br>BLIP_MODIFIER_MP_COLOR_5<br>BLIP_MODIFIER_MP_COLOR_6<br>BLIP_MODIFIER_MP_COLOR_7 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_017.jpeg)
BLIP_MODIFIER_MP_COLOR_8<br>BLIP_MODIFIER_MP_COLOR_9<br>BLIP_MODIFIER_MP_COLOR_10<br>BLIP_MODIFIER_MP_COLOR_11<br>BLIP_MODIFIER_MP_COLOR_12<br>BLIP_MODIFIER_MP_COLOR_13<br>BLIP_MODIFIER_MP_COLOR_14<br>BLIP_MODIFIER_MP_COLOR_15<br>BLIP_MODIFIER_MP_COLOR_16<br>BLIP_MODIFIER_MP_COLOR_17 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_018.jpeg)
BLIP_MODIFIER_MP_COLOR_18<br>BLIP_MODIFIER_MP_COLOR_19<br>BLIP_MODIFIER_MP_COLOR_20<br>BLIP_MODIFIER_MP_COLOR_21<br>BLIP_MODIFIER_MP_COLOR_22<br>BLIP_MODIFIER_MP_COLOR_23<br>BLIP_MODIFIER_MP_COLOR_24<br>BLIP_MODIFIER_MP_COLOR_25<br>BLIP_MODIFIER_MP_COLOR_26<br>BLIP_MODIFIER_MP_COLOR_27 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_019.jpeg)
BLIP_MODIFIER_MP_COLOR_28<br>BLIP_MODIFIER_MP_COLOR_29<br>BLIP_MODIFIER_MP_COLOR_30<br>BLIP_MODIFIER_MP_COLOR_31<br>BLIP_MODIFIER_MP_COLOR_32<br>BLIP_MODIFIER_MP_DEADEYE<br>BLIP_MODIFIER_MP_DOWNED<br>BLIP_MODIFIER_MP_ENEMY_HOLDING<br>BLIP_MODIFIER_MP_FREE_ROAM_EE_PLAYER_DISAPPEARING<br>BLIP_MODIFIER_MP_FREE_ROAM_MISSION_PLAYER_DISAPPEARING | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_020.jpeg)
BLIP_MODIFIER_MP_FREE_ROAM_PLAYER_DISAPPEARING<br>BLIP_MODIFIER_MP_FRIENDLY_HOLDING<br>BLIP_MODIFIER_MP_HOT_BLIP<br>BLIP_MODIFIER_MP_HUNTER<br>BLIP_MODIFIER_MP_JOB_PLAYER_FADE<br>BLIP_MODIFIER_MP_JOB_PLAYER_FADE_THREAT<br>BLIP_MODIFIER_MP_MARKED_FOR_DEATH<br>BLIP_MODIFIER_MP_NEUTRAL<br>BLIP_MODIFIER_MP_OBJECTIVE<br>BLIP_MODIFIER_MP_OBJECTIVE_ENEMY | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_021.jpeg)
BLIP_MODIFIER_MP_OBJECTIVE_FRIENDLY<br>BLIP_MODIFIER_MP_OBJECTIVE_NEUTRAL<br>BLIP_MODIFIER_MP_OVERLAY_ANIMAL<br>BLIP_MODIFIER_MP_OVERLAY_SEDATED<br>BLIP_MODIFIER_MP_PLAYER<br>BLIP_MODIFIER_MP_PLAYER_AGGRESSION<br>BLIP_MODIFIER_MP_PLAYER_ALLY<br>BLIP_MODIFIER_MP_PLAYER_ALLY_WOUNDED<br>BLIP_MODIFIER_MP_PLAYER_BAG<br>BLIP_MODIFIER_MP_PLAYER_CONTROL | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_022.jpeg)
BLIP_MODIFIER_MP_PLAYER_COOP<br>BLIP_MODIFIER_MP_PLAYER_DISAPPEARING<br>BLIP_MODIFIER_MP_PLAYER_ENEMY<br>BLIP_MODIFIER_MP_PLAYER_FORCE_BLIPPED<br>BLIP_MODIFIER_MP_PLAYER_KING<br>BLIP_MODIFIER_MP_PLAYER_LOS_ONLY<br>BLIP_MODIFIER_MP_PLAYER_NEUTRAL<br>BLIP_MODIFIER_MP_PLAYER_SOCIAL<br>BLIP_MODIFIER_MP_PLAYER_UNAVAILABLE<br>BLIP_MODIFIER_MP_PLAYER_WINNING | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_023.jpeg)
BLIP_MODIFIER_MP_PLAYER_WITH_BOUNTY<br>BLIP_MODIFIER_MP_REVIVE<br>BLIP_MODIFIER_MP_RIVAL_RACER<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_1<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_2<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_3<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_4<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_5<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_6<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_7 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_024.jpeg)
BLIP_MODIFIER_MP_SUPPLIES_BASE_8<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_9<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_10<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_11<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_12<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_13<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_14<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_15<br>BLIP_MODIFIER_MP_SUPPLIES_BASE_16<br>BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_1 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_025.jpeg)
BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_2<br>BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_3<br>BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_4<br>BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_5<br>BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_6<br>BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_7<br>BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_8<br>BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_9<br>BLIP_MODIFIER_MP_SUPPLIES_OUTLINE_COLOR_10<br>BLIP_MODIFIER_MP_TEAM_COLOR_1 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_026.jpeg)
BLIP_MODIFIER_MP_TEAM_COLOR_2<br>BLIP_MODIFIER_MP_TEAM_COLOR_3<br>BLIP_MODIFIER_MP_TEAM_COLOR_4<br>BLIP_MODIFIER_MP_TEAM_COLOR_5<br>BLIP_MODIFIER_MP_TEAM_COLOR_6<br>BLIP_MODIFIER_MP_TEAM_COLOR_7<br>BLIP_MODIFIER_MP_TEAM_COLOR_8<br>BLIP_MODIFIER_MP_WHITE_FLAG<br>BLIP_MODIFIER_NEUTRAL_AREA_ON_SNOW<br>BLIP_MODIFIER_NEUTRAL_ON_GUARD | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_027.jpeg)
BLIP_MODIFIER_OBJECTIVE<br>BLIP_MODIFIER_OBJECTIVE_GET_CLOSE<br>BLIP_MODIFIER_OBJECTIVE_LOW_CATEGORY<br>BLIP_MODIFIER_OPEN_RACE_CHECKPOINT<br>BLIP_MODIFIER_OUTSIDE_TOD<br>BLIP_MODIFIER_OVERLAY_1<br>BLIP_MODIFIER_OVERLAY_2<br>BLIP_MODIFIER_OVERLAY_3<br>BLIP_MODIFIER_OVERLAY_4<br>BLIP_MODIFIER_OVERLAY_5 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_028.jpeg)
BLIP_MODIFIER_OVERLAY_6<br>BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_1<br>BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_2<br>BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_3<br>BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_4<br>BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_5<br>BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_6<br>BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_7<br>BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_8<br>BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_9 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_029.jpeg)
BLIP_MODIFIER_OVERLAY_RING_MP_COLOR_10<br>BLIP_MODIFIER_OVERLAY_SADDLE<br>BLIP_MODIFIER_OVERLAY_SADDLE_STOLEN<br>BLIP_MODIFIER_OVERLAY_WHITE_1<br>BLIP_MODIFIER_OVERLAY_WHITE_2<br>BLIP_MODIFIER_OVERLAY_WHITE_3<br>BLIP_MODIFIER_OVERLAY_WHITE_4<br>BLIP_MODIFIER_OVERLAY_WHITE_5<br>BLIP_MODIFIER_OVERLAY_WHITE_6<br>BLIP_MODIFIER_OVERLAY_WHITE_7 | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_030.jpeg)
BLIP_MODIFIER_OVERLAY_WHITE_8<br>BLIP_MODIFIER_OVERLAY_WHITE_9<br>BLIP_MODIFIER_OVERLAY_WHITE_10<br>BLIP_MODIFIER_OVERLAY_WHITE_11<br>BLIP_MODIFIER_OVERLAY_WHITE_12<br>BLIP_MODIFIER_OVERLAY_WHITE_13<br>BLIP_MODIFIER_OVERLAY_WHITE_14<br>BLIP_MODIFIER_OVERLAY_WHITE_15<br>BLIP_MODIFIER_OVERLAY_WHITE_16<br>BLIP_MODIFIER_PARTY | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_031.jpeg)
BLIP_MODIFIER_PICKUP_NEW<br>BLIP_MODIFIER_PICKUP_PLACEMENT<br>BLIP_MODIFIER_PICKUP_SURVIVAL_MODES<br>BLIP_MODIFIER_PICKUP_UNAVAILABLE<br>BLIP_MODIFIER_PICKUP_WEAPON_LEGENDARY<br>BLIP_MODIFIER_PICKUP_WEAPON_NEW<br>BLIP_MODIFIER_PICKUP_WEAPON_OF_CHOICE<br>BLIP_MODIFIER_PICKUP_WEAPON_OWNED<br>BLIP_MODIFIER_PICKUP_WEAPON_RARE<br>BLIP_MODIFIER_PING_GUNSHOT | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_032.jpeg)
BLIP_MODIFIER_PLAYER_HORSE_HITCHED<br>BLIP_MODIFIER_PLAYER_HORSE_INACTIVE<br>BLIP_MODIFIER_PLAYER_HORSE_IN_RANGE<br>BLIP_MODIFIER_PLAYER_HORSE_IN_RANGE_WHISTLE<br>BLIP_MODIFIER_PLAYER_HORSE_OUT_OF_RANGE<br>BLIP_MODIFIER_PLAYER_HORSE_OUT_OF_RANGE_WHISTLE<br>BLIP_MODIFIER_POSSE_ALLY<br>BLIP_MODIFIER_POSSE_ALLY_OWNED<br>BLIP_MODIFIER_POSSE_ENEMY<br>BLIP_MODIFIER_POSSE_ENEMY_OWNED | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_033.jpeg)
BLIP_MODIFIER_POSSE_NEUTRAL_OWNED<br>BLIP_MODIFIER_PREDATOR<br>BLIP_MODIFIER_PREDATOR_5<br>BLIP_MODIFIER_PREDATOR_10<br>BLIP_MODIFIER_PULSE_FOREVER<br>BLIP_MODIFIER_PULSE_THREE_TIMES<br>BLIP_MODIFIER_PVP_TARGET<br>BLIP_MODIFIER_PVP_TARGET_TRACKED<br>BLIP_MODIFIER_RACE_CHECKPOINT_ALT<br>BLIP_MODIFIER_RADAR_EDGE_ALWAYS | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_034.jpeg)
BLIP_MODIFIER_RADAR_EDGE_NEVER<br>BLIP_MODIFIER_RADAR_EDGE_PAUSE_MAP_NEVER<br>BLIP_MODIFIER_SCALE_1<br>BLIP_MODIFIER_SCALE_2<br>BLIP_MODIFIER_SELECTED_UP_SCALE<br>BLIP_MODIFIER_SHOP_UNAVAILABLE<br>BLIP_MODIFIER_SHOW_HEIGHT<br>BLIP_MODIFIER_SHRINK_WARNING_1<br>BLIP_MODIFIER_SHRINK_WARNING_2<br>BLIP_MODIFIER_SP_DOWNED | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_035.jpeg)
BLIP_MODIFIER_TEMP_HORSE_HITCHED<br>BLIP_MODIFIER_TEST_GPS_MODULE<br>BLIP_MODIFIER_TEXT_ONLY<br>BLIP_MODIFIER_TOD_DAYTIME_ONLY<br>BLIP_MODIFIER_TOD_NIGHTTIME_ONLY<br>BLIP_MODIFIER_TOWN_POSSE_MEMBER<br>BLIP_MODIFIER_TRACKING<br>BLIP_MODIFIER_TRAIN_MISSION<br>BLIP_MODIFIER_UNDISCOVERED<br>BLIP_MODIFIER_URGENT | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_036.jpeg)
BLIP_MODIFIER_URGENT_ALERT<br>BLIP_MODIFIER_URGENT_ALERT_INTERNAL<br>BLIP_MODIFIER_VERYHIGH_CATEGORY<br>BLIP_MODIFIER_WANTED_PULSE_1<br>BLIP_MODIFIER_WANTED_PULSE_2<br>BLIP_MODIFIER_WANTED_PULSE_3<br>BLIP_MODIFIER_WANTED_PULSE_4<br>BLIP_MODIFIER_WANTED_PULSE_5<br>BLIP_MODIFIER_WILDERNESS_CHEST_LONG<br>BLIP_MODIFIER_WITNESS_IDENTIFIED | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_037.jpeg)
BLIP_MODIFIER_WITNESS_INVESTIGATING<br>BLIP_MODIFIER_WITNESS_UNIDENTIFIED | ![screen_1.png](https://femga.com:8080/images/samples/blip_modifiers/blip_modifier_038.jpeg)
