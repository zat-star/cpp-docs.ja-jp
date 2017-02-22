---
title: "プロパティ ページの指定 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISpecifyPropertyPages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISpecifyPropertyPages メソッド"
  - "プロパティ ページ, 指定"
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# プロパティ ページの指定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロールを作成する場合、通常、コントロールのプロパティを設定するために使用できるプロパティ ページに関連する必要があります。  コントロールのコンテナーは検索するために、コントロールのプロパティを設定するには、プロパティ ページを使用できる **ISpecifyPropertyPages** のインターフェイスを使用します。  コントロールのこのインターフェイスを実装する必要があります。  
  
 ATL を使用して **ISpecifyPropertyPages** を実装するには、次の手順を実行する:  
  
1.  [ISpecifyPropertyPagesImpl](../Topic/ISpecifyPropertyPagesImpl%20Class.md)からクラスを派生します。  
  
2.  クラスの COM マップに **ISpecifyPropertyPages** のエントリを追加します。  
  
3.  は、コントロールに関連付けられている各ページのプロパティ マップに [PROP\_PAGE](../Topic/PROP_PAGE.md) のエントリを追加します。  
  
> [!NOTE]
>  標準コントロールを [&#91;ATL コントロール ウィザード&#93;](../atl/reference/atl-control-wizard.md)を使用して生成した場合、プロパティ `PROP_PAGE` マップにエントリを追加する場合にのみ必要があります。  ウィザードは、他の手順を行うために必要なコードが生成されます。  
  
 行儀は、コンテナーはプロパティの `PROP_PAGE` のエントリに対応するのと同じ順序で、指定したプロパティ ページを表示します。  通常は、ユーザーがコントロールと特定のページが最初に表示されるように、プロパティ マップに、カスタム ページのエントリの後に標準のプロパティ ページのエントリを設定する必要があります。  
  
## 例  
 Calendar コントロールの次のクラスは、プロパティがカスタム日付のページと標準色のページを使用して設定できることをコンテナーに通知するために **ISpecifyPropertyPages** のインターフェイスを使用します。  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/CPP/specifying-property-pages_1.h)]  
  
## 参照  
 [プロパティ ページ](../atl/atl-com-property-pages.md)   
 [ATLPages サンプル](../top/visual-cpp-samples.md)