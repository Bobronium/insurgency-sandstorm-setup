# insurgenct-sandstorm-setup
 Stutter-less and performance oriented Insurgency: Sandstorm setup
 
## Engine.ini tweaks
### Texture streaming tweak (remove stutters)
```ini
[TextureStreaming]
BoostPlayerTextures=1.0
AllowStreamingLightmaps=False
r.Streaming.DropMips=0
r.Streaming.LimitPoolSizeToVRAM=0
r.Streaming.MipBias=0
r.Streaming.UseAllMips=1
r.Streaming.UseMaterialData=1
r.Streaming.UseNewMetrics=1
r.Streaming.UsePerTextureBias=1
```
### Various settings for `[/script/engine.renderersettings]` section
### Improve TAA sharpeness and quality
```ini
r.PostProcessAAQuality=5
r.Tonemapper.Sharpen=0.6
r.DepthOfField.FarBlur=0
```
### Another possibele stutters fix
```ini
r.CreateShadersOnLoad=1
r.Shaders.Optimize=1
```
### Disable/criple shadows for performance
```ini
r.Shadow.MaxResolution=2
r.Shadow.DistanceScale=0.001
r.Shadow.CachedShadowsCastFromMovablePrimitives=0
r.ShadowQuality=0
r.Shadow.CSM.MaxCascades=1
r.Shadow.RadiusThreshold=0.1
r.Shadow.CSM.TransitionScale=0
```

### Disable bloom/blur/volumetric lighting
```ini
r.BloomQuality=0
r.BlurGBuffer=0
r.VolumetricFog=0
r.VolumetricFog.GridPixelSize=0
r.VolumetricFog.GridSizeZ=0
r.DefaultFeature.AutoExposure=False
r.DefaultFeature.Bloom=False
r.Tonemapper.GrainQuantization=0
r.LightShaftQuality=0
r.RefractionQuality=0
r.LPV.RSMResolution=4
```
### Optimize blur
```ini
r.FastBlurThreshold=0
```
### Other stuff that I have and dunno much about
```ini
r.Streaming.MipBias=0
r.Streaming.PoolSize=4000
r.FinishCurrentFrame=0
r.TranslucencyLightingVolumeDim=6
r.DetailMode=0
r.TranslucencyVolumeBlur=0
r.GBufferFormat=3
r.VirtualTexture=1
r.VirtualTextureReducedMemory=1
s.AsyncLoadingThreadEnabled=1
r.SkinCache.Mode=1
r.ClearWithExcludeRects=2
r.OptimizeForUAVPerformance=1
r.CreateShadersOnLoad=1
r.Shaders.Optimize=1
```
### Random settings from random optimization guides
```ini
[ConsoleVariables]
AllowAsyncRenderThreadUpdates=1
AllowAsyncRenderThreadUpdates=1
AllowAsyncRenderThreadUpdatesDuringGamethreadUpdates=1
AllowAsyncRenderThreadUpdatesDuringGamethreadUpdates=1
AllowAsyncRenderThreadUpdatesEditor=1
AllowAsyncRenderThreadUpdatesEditor=1
r.DeferSkeletalDynamicDataUpdateUntilGDME=1
r.DeferUniformBufferUpdatesUntilVisible=1
r.DoInitViewsLightingAfterPrepass=1
r.SkinCache.Mode=1
r.ClearWithExcludeRects=2
r.CreateShadersOnLoad=1
r.StreamingPoolSize=-1
```

```ini
[ConsoleVariables]
AllowAsyncRenderThreadUpdates=1
AllowAsyncRenderThreadUpdates=1
AllowAsyncRenderThreadUpdatesDuringGamethreadUpdates=1
AllowAsyncRenderThreadUpdatesDuringGamethreadUpdates=1
AllowAsyncRenderThreadUpdatesEditor=1
AllowAsyncRenderThreadUpdatesEditor=1
r.DeferSkeletalDynamicDataUpdateUntilGDME=1
r.DeferUniformBufferUpdatesUntilVisible=1
r.DoInitViewsLightingAfterPrepass=1
r.SkinCache.Mode=1
r.ClearWithExcludeRects=2
r.CreateShadersOnLoad=1
r.StreamingPoolSize=-1
```

```ini
[/script/engine.garbagecollectionsettings]
TimeBetweenPurgingPendingKillObjects=15
```

```ini
[/script/engine.engine]
bUseVSync=false
MaxPixelShaderAdditiveComplexityCount=128
MaxES2PixelShaderAdditiveComplexityCount=45
IdealLightMapDensity=0.02
MaxLightMapDensity=0.05
```

```ini
[WindowsApplication.Accessibility]
StickyKeysHotkey=True
ToggleKeysHotkey=True
FilterKeysHotkey=True
StickyKeysConfirmation=True
ToggleKeysConfirmation=True
FilterKeysConfirmation=True
```
## Launch options
- `-dx12`

	Forces usage of DirectX 12. Huge performance boost in avg FPS.
	
	Known issues:
	- Game ocasionally will crash reporing D3D error when Alt-Tabbing while loading a new map.
    - Flickering artifacts on bushes on some maps.

- `-dx9`

	Forces usage of DirectX 9. Huge performance boost in avg FPS.
	
	Known issues:
	- Game visuals are worse in comparison to DX11/DX12.
    - Alt-Tabbing is slow and flickery.
	
### Placebo launch options
Won't hurt. Won't help either. 
- `-USEALLAVAILABLECORES` - so far I didn't notice any changes in performance when using this. [Some comment](https://steamcommunity.com/app/581320/discussions/0/2143092024478001183/?ctp=2#c3196993831804372917) 
- `-NoGlobalInvalidation` - this was in fact a helpful option that fixed stuttering in [1.7.1 update](https://store.steampowered.com/news/app/581320/view/3881493771286319979). It was recommended by devs as a temporary workaround, until [1.7.1 Hotfix 2](https://store.steampowered.com/news/app/581320/view/2789374424361935598) was released where global invalidation has been removed. So now this option is obsolete. 
- `-malloc=tbbmalloc/system` - doesn't do shit in UE4.

## Common
#### Launch the game via Steam from launch panel
Create a shortcut with following path and drag it to launch panel:

`%windir%\explorer.exe steam://rungameid/581320`

For better looks, you can give it Insurgenct executable icon. 
