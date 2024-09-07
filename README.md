# RW.AnimatedMotes
A port of Toranns Magic Frameworks (Graphic_Animation) class, allowing for traditional sprite animations, all credit goes to https://github.com/TorannD/TMagic



```xml
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


	 /*
	 * This file contains code derived from the TMagic mod by TorannD.
	 * Original source: https://github.com/TorannD/TMagic
	 * 
	 * TMagic is licensed under the BSD 3-Clause License:
	 * 
	 * Copyright (c) 2019, TorannD
	 * All rights reserved.
	 * 
	 * Redistribution and use in source and binary forms, with or without
	 * modification, are permitted provided that the following conditions are met:
	 * 
	 * 1. Redistributions of source code must retain the above copyright notice, this
	 *    list of conditions and the following disclaimer.
	 * 
	 * 2. Redistributions in binary form must reproduce the above copyright notice,
	 *    this list of conditions and the following disclaimer in the documentation
	 *    and/or other materials provided with the distribution.
	 * 
	 * 3. Neither the name of the copyright holder nor the names of its
	 *    contributors may be used to endorse or promote products derived from
	 *    this software without specific prior written permission.
	 * 
	 * THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
	 * AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
	 * IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
	 * DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
	 * FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
	 * DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
	 * SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
	 * CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
	 * OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
	 * OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
	 */
