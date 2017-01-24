---
title: "CD2DTextLayout クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DTextLayout"
  - "afxrendertarget/CD2DTextLayout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DTextLayout クラス"
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
caps.latest.revision: 16
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DTextLayout クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

IDWriteTextLayout のラッパー。  
  
## 構文  
  
```  
class CD2DTextLayout : public CD2DResource;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DTextLayout::CD2DTextLayout](../Topic/CD2DTextLayout::CD2DTextLayout.md)|CD2DTextLayout オブジェクトを構築します。|  
|[CD2DTextLayout::~CD2DTextLayout](../Topic/CD2DTextLayout::~CD2DTextLayout.md)|デストラクターです。  D2D テキスト レイアウト オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DTextLayout::Create](../Topic/CD2DTextLayout::Create.md)|CD2DTextLayout を作成します   \([CD2DResource::Create](../Topic/CD2DResource::Create.md) をオーバーライドします\)。|  
|[CD2DTextLayout::Destroy](../Topic/CD2DTextLayout::Destroy.md)|CD2DTextLayout オブジェクトを破棄します   \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) をオーバーライドします\)。|  
|[CD2DTextLayout::Get](../Topic/CD2DTextLayout::Get.md)|IDWriteTextLayout インターフェイスを返します。|  
|[CD2DTextLayout::GetFontFamilyName](../Topic/CD2DTextLayout::GetFontFamilyName.md)|指定した位置にあるテキストのフォント ファミリ名をコピーします。|  
|[CD2DTextLayout::GetLocaleName](../Topic/CD2DTextLayout::GetLocaleName.md)|指定した位置にあるテキストのロケール名を取得します。|  
|[CD2DTextLayout::IsValid](../Topic/CD2DTextLayout::IsValid.md)|リソースの有効性を検証します \([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) をオーバーライドします\)。|  
|[CD2DTextLayout::ReCreate](../Topic/CD2DTextLayout::ReCreate.md)|CD2DTextLayout を再作成します。  \([CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md) をオーバーライドします\)。|  
|[CD2DTextLayout::SetFontFamilyName](../Topic/CD2DTextLayout::SetFontFamilyName.md)|指定したテキスト範囲内のテキストの null で終わるフォント ファミリ名を設定します。|  
|[CD2DTextLayout::SetLocaleName](../Topic/CD2DTextLayout::SetLocaleName.md)|指定したテキスト範囲内のテキストのロケール名を設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DTextLayout::operator IDWriteTextLayout\*](../Topic/CD2DTextLayout::operator%20IDWriteTextLayout*.md)|IDWriteTextLayout インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CD2DTextLayout::m\_pTextLayout](../Topic/CD2DTextLayout::m_pTextLayout.md)|IDWriteTextLayout へのポインター。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)