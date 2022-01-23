# Insurgency: Sandstorm
 Stutter-less and performance oriented Insurgency: Sandstorm setup


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
- `-malloc=tbbmalloc/system` - doesn't do shit in UE4. `%windir%\explorer.exe steam://rungameid/581320`
