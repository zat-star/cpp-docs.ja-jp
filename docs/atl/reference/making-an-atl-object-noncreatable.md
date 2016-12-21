---
title: "ATL オブジェクトを作成できないようにする | Microsoft Docs"
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
  - "vc.appwiz.ATL.objects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL プロジェクト, 作成不可オブジェクト"
  - "作成不可 ATL オブジェクト"
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL オブジェクトを作成できないようにする
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL ベースの COM オブジェクトの属性を変更して、クライアントがオブジェクトを直接作成できないように指定できます。  この場合、オブジェクトは直接作成されるのではなく、ほかのオブジェクトに対するメソッド呼び出しを通じて返されます。  
  
### オブジェクトを作成できないようにするには  
  
1.  オブジェクトの [OBJECT\_ENTRY\_AUTO](../Topic/OBJECT_ENTRY_AUTO.md) を削除します。  オブジェクトは作成できないようにして、コントロールを登録する場合は、OBJECT\_ENTRY\_AUTO を [OBJECT\_ENTRY\_NON\_CREATEABLE\_EX\_AUTO](../Topic/OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO.md) に置き換えます。  
  
2.  .idl ファイルのコクラスに属性 [noncreatable](../../windows/noncreatable.md) を追加します。  次に例を示します。  
  
    ```  
    [  
       uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),  
       helpstring("MyObject"),  
      noncreatable  
    ]  
    coclass MyObject  
    {  
       [default] interface IMyInterface;  
    }  
    ```  
  
## 参照  
 [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)   
 [Visual C\+\+ プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)