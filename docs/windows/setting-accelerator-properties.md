---
title: "アクセラレータのプロパティの設定 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクセラレータのプロパティ"
  - "アクセラレータのプロパティのプロパティ [C++]"
  - "Type プロパティ"
  - "Key プロパティ"
  - "Modifier プロパティ"
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# アクセラレータのプロパティの設定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C .NET でアクセラレータのプロパティを設定することができます、 [プロパティ] ウィンドウ](../Topic/Properties%20Window.md) いつでもできます。 また、アクセラレータ エディターを使用して、アクセラレータ テーブルでアクセラレータのプロパティを変更することもできます。 プロパティ ウィンドウを使用しても、アクセラレータ エディターを使用しても、変更の結果は同じです。編集はすぐにアクセラレータ テーブルに反映されます。  
  
 各アクセラレータの 3 つのプロパティがある [ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-    [[修飾子] プロパティ](../Topic/Accelerator%20Modifier%20Property.md) アクセラレータのショートカット キーを設定します。  
  
    > [!NOTE]
    >  プロパティ ウィンドウでは、このプロパティは 3 つの独立したブール型プロパティ (Alt、Ctrl、Shift) として表示され、すべて個別に制御できます。  
  
-    [キー プロパティ](../Topic/Accelerator%20Key%20Property.md) アクセラレータとして使用する実際のキーを設定します。  
  
-    [プロパティを入力して](../windows/accelerator-type-property.md) キーが仮想 (VIRTKEY) または ASCII]/[ANSI として解釈されるかどうかを決定します。  
  
 マネージ プロジェクトにリソースを追加する方法については、『 [.NET Framework 開発者ガイド](../Topic/Resources%20in%20Desktop%20Apps.md) 』の「 *アプリケーションのリソース* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [Walkthrough: Using Resources for Localization with ASPします。NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [定義済みのアクセラレータ キー](../windows/predefined-accelerator-keys.md)   
 [リソース エディター](../mfc/resource-editors.md)   
 [アクセラレータ エディター](../Topic/Accelerator%20Editor.md)