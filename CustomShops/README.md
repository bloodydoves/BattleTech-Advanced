# CustomShops

CustomShops - Mod that allow create and manage shops, taking all ui and other "backstage" work 

Also it add some optional features, like BuyBack shop and MultiBuy to vanila shops

## Basic Settings(mod.json)

### Debug options

`"AddLogPrefix" : false` - add [CShops] prefix to log(for use with FYLS log aggregator)

`"DebugType" : "ShopInterface, DInfo.SaveLoad, DInfo.RefreshShop, DInfo.TabSwitch` - how detail debug info to show

`"DEBUG_FactionShopAlwaysAvaliable" : false` - faction shop always usable if present in system

`"DEBUG_BlackMarketAlwaysAvaliable" : false` - same for black market

### Main Options

`"SystemShop" : true` - enables prebuilded replacement for SystemShop

`"FactionShop" : true` - enables prebuilded replacement for FactionShop

`"BlackMarketShop" : true` - enables prebuilded replacement for BlackMarket

if you replace this shop in your mod with own variants(like DynamicShops do for example) - set to false or you get all 6 variants. also if you disable it you still not get vanila shops, so if no replacement - no shops at all

`"BuyBackShop" : true` - enable BuyBack shop

`"AllowMultiSell" : true` - enable MultiSell dialog

`"AllowMultiBuy" : true` - enable MultiBuy dialog

`"ShowConfirm" : true` - Show confirm if purshase/sell price higher then next option(only for single item operation, for multi item - dialog is shown)
 
`"ConfirmLowLimit" : 100000` - lower limit of price for confirm dialog to show
 
`"FactionShopAdjustment" : -0.25` - static faction shop discount. in vanila game this is 0.1(also vanila have this based on your reputation but shop avaliable only if allied so it anyway static). 

## Creating own shops(Dll modding)

To create own shop you need reference CustomShops, implement interfaces from it to describe it behaviour and register your shop in CustomShops using CustomShops.Control.RegisterShop()

### Interfaces

###IShopDesctiptor

base interface for shop, need to be implemented

```
    public interface IShopDescriptor
    {
        string Name { get; }
        string TabText { get; }
        string ShopPanelImage { get; }
        public Color IconColor { get; }
        public Color ShopColor { get; }
        public bool Exists { get; }
        public bool CanUse { get; }


        void RefreshShop();
    }
```

Name - using to identify your shop. 

TabText - using for tab caption in shop interface

ShopPanelImage - using for image on store panel. most game shops use same uixTxrSpot_Store image

IconColor - Color of icon on tab(use white if your icon already colored)

ShopColor - Color of shop panel(use dim and dark colors there)

Exists - checks if this shop exists in system, in simple - need to create shop tab in this system

CanUse - check if shop avaliable for player - if return false tab still be created but will be disabled(like black market when you not have access to it)


RefreshShop - called when shop need to refresh its inventory(also on shop initilisation)

### IconInterfaces

Define what icon use for shop tab. if none implemented - default planet icon used

```
    public interface ISpriteIcon
    {
        Sprite Sprite { get; }
    }
    public interface ITextIcon
    {
        string SpriteID { get; }
    }
```

ISpriteIcon - define icon by sprite
ITextIcon - define icon by ressourseid. given id will be loaded and used as icon

### ISaveShop

Define that shop should be saved and loaded into savegame. if not used - on game load shop will be refreshed
If shop not found in save game - it will be refreshed

```
    public interface ISaveShop
    {
        Shop GetShopToSave();
        void SetLoadedShop(Shop shop);
    }
```
GetShopToSave - should return Battletech.Shop to save(basicly you need Shop.ActiveInventory)

SetLoadedShop - Called when shop successfully loaded

### IDefaultShop

Define Shop to use for shop inventory and purshase operations(currently only avaliable interface of this type. more, that dont require Battletech.Shop, interfaces in development)
```
    public interface IDefaultShop
    {
        Shop ShopToUse { get; }
    }
```

### IListShop

Define shop that keap its content in List not Shop class(you still need convert it to Shop for savegame)
```
    public interface IListShop
    {
        List<ShopDefItem> Items { get; }
    }
```

### ICustomPurshase

Define shop with custom purshase handler. Purshase called when item already purshased and removed from shop interface. To finalize pursahse you need implement removing item from 
shop itself, adding funds and item, and other stuff you need. You can use `CustomShops.UIControl.DefaultPurshase(this, item, quantity)`(defined for both list and default shops) and implement only 
custom stuff if any changes on usual buy pursahse process not needed

```
    public interface ICustomPurshase
    {
        void Purshase(ShopDefItem item, int quantity);
    }
```


### IRelatedFaction

Base interface for other interfaces that require faction associated with shop. do nothing itself

```
 public interface IRelatedFaction
    {
        BattleTech.FactionValue RelatedFaction { get; }
    }
```

### MiniFactionWidget interfaces

used to fill MiniFactionWidget(faction heraldy with discount text and reputation icon on top of shop image)

```
    public interface IFillWidgetFromFaction : IRelatedFaction
    {
    }

    public interface ICustomFillWidget
    {
        void FillFactionWidget(ShopScreenHelper helper);
    }
```
IFillWidgetFromFaction - fill widget from related faction

ICustomFillWidget - allow to custom fill this widget. gives helper class with access to all ui elements of it

### Price and Discount interfaces

This interface control how prices and discounts handle. Full price is base price * discount;


Price interfaces 
```
    public interface IDefaultPrice
    {
    }

    public interface ICustomPrice
    {
        public int GetPrice(TypedShopDefItem item);
    }
```

IDefaultPrice - return item.Description.Cost(mechdef.MechPartCost for parts)

ICustomPrice - should return base price of given item. TypedShopDefItem - ShopDefItem with cashed MechComponentDef/MechDef/Description to use

Discount interfaces 
```
	public interface IDiscountFromFaction : IRelatedFaction
    {
    }

    public interface ICustomDiscount
    {
        public float GetDiscount(TypedShopDefItem item);
    }

    public interface INoDiscount
    {
    }
```
IDiscountFromFaction - discount based on reputation of related faction

INoDiscount - no discount(allways 1)

ICustomDiscount - return discount for item. if item is null - should return general discount for shop(used for MiniFactionWidget)

## ShopRefresh

To fill/refresh shop content IShopDescriptor.RefreshShop() called. You can subscribe your shop to predefined events(case indiferent)
```
	"Daily"
    "SystemChange"
    "MonthEnd"
    "ContractComplete"
    "OwnerChange"
```

while register shop set a second parameter to enumeration of requered events like
`CustomShops.Control.RegisterShop(myshop, new string[] { "systemchange", "monthend" });`

Also you can call RefreshShop directly when needed for some custom refreshes or register new event with
`CustomShops.Control.RegisterRefreshEvent("EventName")`
and then call with
`CustomShops.Control.RefreshShops("EventName");`
