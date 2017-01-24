---
title: "LOGPEN 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LOGPEN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LOGPEN 構造体"
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# LOGPEN 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

 `LOGPEN` 構造体は、スタイル、幅、およびペンの色を定義、描画に使用する描画オブジェクトの直線し罫線します。  [CPen::CreatePenIndirect](../Topic/CPen%20Class.md#cpen__createpenindirect) 関数は、 `LOGPEN` 構造体。  
  
## <a name="syntax"></a>構文  
  
```  
 
    typedef struct tagLOGPEN {  /* lgpn */  
    UINT lopnStyle;  
    POINT lopnWidth;  
    COLORREF lopnColor;  
} LOGPEN;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *lopnStyle*  
 ペンの種類を指定します。 このメンバーは、次の値のいずれかになります。  
  
- **きは** ソリッド ペンを作成します。  
  
- **PS_DASH** 破線のペンを作成します。 (ペンの幅が 1 である場合にのみ有効です。)  
  
- **PS_DOT** ピリオドで区切られたペンを作成します。 (ペンの幅が 1 である場合にのみ有効です。)  
  
- **PS_DASHDOT** の代替ダッシュとドットでペンを作成します。 (ペンの幅が 1 である場合にのみ有効です。)  
  
- **PS_DASHDOTDOT** の代替ダッシュと 2 つのドットでペンを作成します。 (ペンの幅が 1 である場合にのみ有効です。)  
  
- **必ず** null ペンを作成します。  
  
- **ペン** GDI 関数外接する四角形を指定することによって生成される、閉じた図形のフレーム内の行を描画するペンを作成 (たとえば、 **楕円**, 、**四角形**, 、`RoundRect`, 、`Pie`, 、および `Chord` メンバー関数)。 外接する四角形が指定されていない関数の出力 GDI を使用してこのスタイルを使用する場合 (たとえば、 `LineTo` メンバー関数)、ペンの描画領域は、フレームによって制限されません。  
  
     ペンがある場合、 **ペン** スタイルおよび色の論理テーブルで使用する色に一致しない色ディザー カラーでペンを描画します。  **きは** にディザー カラー ペンを作成するのには、ペンのスタイルを使用できません。  **ペン** スタイルは **きは** ペンの幅が 1 以下である場合。  
  
     ときに、 **ペン** スタイルが以外の関数によって生成される GDI オブジェクトと共に使用される **楕円**, 、**四角形**, 、および `RoundRect`, 、行あります完全に指定したフレームの中。  
  
 *lopnWidth*  
 論理ユニットでは、ペンの幅を指定します。 場合、 **lopnWidth** メンバーが 0 のペンが現在のマッピング モードに関係なくラスター デバイス上の 1 ピクセル場合、です。  
  
 *lopnColor*  
 ペンの色を指定します。  
  
## <a name="remarks"></a>解説  
  **Y** 内の値、 [ポイント](../../mfc/reference/point-structure1.md) の構造体、 **lopnWidth** メンバーは使用されません。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../Topic/CPen%20Class.md#cpen__createpenindirect)

