---
title: "COleVariant クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "オートメーション, パラメーターの型"
  - "COleVariant クラス"
  - "VARIANT データ型"
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleVariant クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バリアント データ型をカプセル化します。  
  
## 構文  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleVariant::COleVariant](../Topic/COleVariant::COleVariant.md)|`COleVariant` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleVariant::Attach](../Topic/COleVariant::Attach.md)|`COleVariant`に **VARIANT** をアタッチします。|  
|[COleVariant::ChangeType](../Topic/COleVariant::ChangeType.md)|この `COleVariant` の異なるオブジェクトの型を変更します。|  
|[COleVariant::Clear](../Topic/COleVariant::Clear.md)|この `COleVariant` オブジェクトをクリアします。|  
|[COleVariant::Detach](../Topic/COleVariant::Detach.md)|`COleVariant` から **VARIANT** をデタッチし、**VARIANT**を返します。|  
|[COleVariant::GetByteArrayFromVariantArray](../Topic/COleVariant::GetByteArrayFromVariantArray.md)|既存の異なる配列からバイト配列を取得します。|  
|[COleVariant::SetString](../Topic/COleVariant::SetString.md)|特定の型 \(通常は ANSI に文字列を設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[COleVariant::operator LPCVARIANT](../Topic/COleVariant::operator%20LPCVARIANT.md)|`LPCVARIANT`に `COleVariant` の値を変換します。|  
|[COleVariant::operator LPVARIANT](../Topic/COleVariant::operator%20LPVARIANT.md)|`LPVARIANT`に `COleVariant` のオブジェクトを変換します。|  
|[COleVariant::operator \=](../Topic/COleVariant::operator%20=.md)|`COleVariant` 値をコピーします。|  
|[COleVariant::operator \=\=](../Topic/COleVariant::operator%20==.md)|`COleVariant` の 2 個の値を比較します。|  
|[COleVariant::operator \<\<、\>\>](../Topic/COleVariant::operator%20%3C%3C,%20%3E%3E.md)|`COleVariant` の値を `CArchive` か `CDumpContext` に出力し、`CArchive`から `COleVariant` のオブジェクトを取得します。|  
  
## 解説  
 このデータ型は、OLE オートメーションで使用されます。  具体的には、[DISPPARAMS](http://msdn.microsoft.com/ja-jp/a16e5a21-766e-4287-b039-13429aa78f8b) の構造は **VARIANT** の構造体の配列へのポインターが格納されます。  **DISPPARAMS** の構造が [IDispatch::Invoke](http://msdn.microsoft.com/ja-jp/964ade8e-9d8a-4d32-bd47-aa678912a54d)にパラメーターを渡すために使用されます。  
  
> [!NOTE]
>  このクラスは **VARIANT** の構造から派生します。  これを呼び出す **VARIANT** を **VARIANT** の構造体のデータ メンバーがアクセスできるデータ メンバーの `COleVariant`で、パラメーターの `COleVariant` を渡すことができることを意味します。  
  
 2 種類の関連 MFC クラス [COleCurrency](../Topic/COleCurrency%20Class.md)[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) とは異なるデータ型 **CURRENCY** \(`VT_CY`\) と **date** \(`VT_DATE`\) をカプセル化します。  `COleVariant` のクラスは、DAO クラスで広く使用されています; このクラスの一般的な使用など、[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) と [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)については、これらのクラスを参照してください。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [VARIANT](http://msdn.microsoft.com/ja-jp/e305240e-9e11-4006-98cc-26f4932d2118)、[CURRENCY](http://msdn.microsoft.com/ja-jp/5e81273c-7289-45c7-93c0-32c1553f708e)、[DISPPARAMS](http://msdn.microsoft.com/ja-jp/a16e5a21-766e-4287-b039-13429aa78f8b)と [IDispatch::Invoke](http://msdn.microsoft.com/ja-jp/964ade8e-9d8a-4d32-bd47-aa678912a54d) のエントリを参照してください。  
  
 `COleVariant` クラスの詳細および OLE オートメーションの使用については、「" [&#91;オートメーション&#93;](../../mfc/automation.md)の OLE オートメーションのパラメーターの受け渡し」を参照してください。  
  
## 継承階層  
 `tagVARIANT`  
  
 `COleVariant`  
  
## 必要条件  
 **ヘッダー :** afxdisp.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)