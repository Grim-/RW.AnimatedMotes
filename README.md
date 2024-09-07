# Animated Motes

This code is derived from the TMagic mod by TorannD.
This is simply a port of an existing series of classes found inside RimWorld Of Magic allowing the use of individual images to create an animated mote, all credit belongs to the original developers.

Original source: https://github.com/TorannD/TMagic

TMagic is licensed under the BSD 3-Clause License (full license text at the end of this document).

## Usage Instructions

1. Include this mod as a dependency of your own mod.

2. When defining motes, use the `AnimatedMotes.Mote_Animation` thing class:
   ```xml
   <thingClass>AnimatedMotes.Mote_Animation</thingClass>
   ```

3. Set the graphicClass to `AnimatedMotes.Graphic_Animated`:
   ```xml
   <graphicClass>AnimatedMotes.Graphic_Animated</graphicClass>
   ```

4. Use `AnimatedMotes.GraphicDataAnimation` for the graphicData class:
   ```xml
   <graphicData Class="AnimatedMotes.GraphicDataAnimation">
   ```
   This custom class extends the standard GraphicData to support animated graphics.

5. For animated motes, use the custom `AnimatedMotes.AnimationDef` instead of ThingDef:
   ```xml
   <AnimatedMotes.AnimationDef ParentName="YourBaseDef">
   ```
   This allows you to use animation-specific fields like `fpsRate` and `maxLoopCount`.

6. The `fpsRate` field determines the frames per second for the animation.

7. The `maxLoopCount` field sets the number of times the animation will loop before stopping.
   If set to 0 or a negative number, the animation will loop indefinitely.

## Example Usage

```xml
<!-- A base mote ThingDef -->
<ThingDef Name="AuraTestBase" Abstract="True">
  <thingClass>AnimatedMotes.Mote_Animation</thingClass>
  <label>Mote</label>
  <category>Mote</category>
  <mote>
    <solidTime>99999999</solidTime>
  </mote>
  <graphicData Class="AnimatedMotes.GraphicDataAnimation">
    <graphicClass>AnimatedMotes.Graphic_Animated</graphicClass>
    <shaderType>Mote</shaderType>
    <drawSize>1</drawSize>
  </graphicData>
  <altitudeLayer>MoteOverhead</altitudeLayer>
  <tickerType>Normal</tickerType>
  <useHitPoints>false</useHitPoints>
  <isSaveable>true</isSaveable>
  <rotatable>false</rotatable>
  <drawOffscreen>true</drawOffscreen>
</ThingDef>

<!-- A custom AnimationDef -->
<AnimatedMotes.AnimationDef ParentName="AuraTestBase">
  <defName>ExpandingAuraMote</defName>
  <graphicData Class="AnimatedMotes.GraphicDataAnimation">
    <texPath>Animations/Aura</texPath>
    <drawSize>3</drawSize>
    <color>(1, 0, 0, 1)</color>
  </graphicData>
  <altitudeLayer>MoteOverhead</altitudeLayer>
  <mote>
    <fadeInTime>0</fadeInTime>
    <solidTime>99999</solidTime>
    <fadeOutTime>0</fadeOutTime>
    <growthRate>0</growthRate>
    <speedPerTime>0</speedPerTime>
  </mote>
  <fpsRate>2</fpsRate>
  <maxLoopCount>2</maxLoopCount>
</AnimatedMotes.AnimationDef>
```

## License

	 
  This file contains code derived from the TMagic mod by TorannD.
  Original source: https://github.com/TorannD/TMagic
  
  TMagic is licensed under the BSD 3-Clause License:
  
  Copyright (c) 2019, TorannD
  All rights reserved.
  
  Redistribution and use in source and binary forms, with or without
  modification, are permitted provided that the following conditions are met:
  
  1. Redistributions of source code must retain the above copyright notice, this
     list of conditions and the following disclaimer.
  
  2. Redistributions in binary form must reproduce the above copyright notice,
     this list of conditions and the following disclaimer in the documentation
     and/or other materials provided with the distribution.
  
  3. Neither the name of the copyright holder nor the names of its
     contributors may be used to endorse or promote products derived from
     this software without specific prior written permission.
  
  THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
  AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
  IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
  DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
  FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
  DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
  SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
  CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
  OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
  OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
	 


