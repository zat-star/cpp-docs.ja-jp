---
title: "エラー トラッピング | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], エラー トラッピング"
  - "エラー トラッピング [C++]"
ms.assetid: c509b089-a542-44be-8f22-dc5832967a48
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# エラー トラッピング
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ バインディング時のエラー トラッピングの発生元として、エラー イベントとエラー オブジェクトの 2 つが挙げられます。  
  
##  <a name="vcreferrortrappingviaerrorevents"></a> エラー イベントによるエラー トラッピング  
 ADO データ コントロールおよび RDO RemoteData コントロールのデータ コントロールには、エラー イベントがあります。  通常は、エラー イベント ハンドラーを設定します。  イベント ハンドラーは、次のようなシグネチャ \(引数の数、順番、および型\) を持ちます。  
  
```  
void CMyDlg::OnErrorAdodc1(long ErrorNumber,  
                           BSTR* FAR Description,  
                           long Scode,  
                           LPCTSTR Source,  
                           LPCTSTR HelpFile,  
                           long HelpContext,  
                           BOOL FAR* fCancelDisplay)  
```  
  
 通常は Description フィールドにデータが設定されます。ErrorNumber フィールドと Scode フィールドには、COM エラーが発生した場合だけ、データが設定されます。  標準のイベント ハンドラーは、Description フィールドをメッセージ ボックスに表示します。  たとえば、次のようになります。  
  
```  
{  
   USES_CONVERSION;     
// note: have to include the ATL file ATLConv.h to use the ATL conversion macros  
   ::AfxMessageBox(OLE2T(*Description), MB_OK);  
}  
```  
  
 ただし、ADO データ コントロールおよび RDO RemoteData コントロールは既にエラー イベントをトラップするように設定されているため、コーディングは不要です。  
  
##  <a name="vcreferrortrappingviaerrorobjects"></a> エラー オブジェクトによるエラー トラッピング  
 ADO と RDO には、エラー オブジェクトがあります。  [ラッパー クラス](../../data/ado-rdo/wrapper-classes.md)を作成すると、RDO RemoteData コントロールはエラー オブジェクト用のラッパー関数を作成します。一方、ADO データ コントロールは、このようなラッパー関数を作成しません。  
  
 ADO データ コントロールは、ADO エラー メッセージを自動的に表示します。  
  
## 参照  
 [Visual C\+\+ で ActiveX コントロールによるデータ連結を行う](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)