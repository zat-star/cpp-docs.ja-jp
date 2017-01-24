---
title: "CMFCMaskedEdit クラス | Microsoft Docs"
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
  - "CMFCMaskedEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMaskedEdit クラス"
  - "CMFCMaskedEdit コンストラクター"
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCMaskedEdit クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCMaskedEdit` クラスは、マスク エディット コントロールをサポートします。これは、ユーザーの入力をマスクと検証し、テンプレートに従って検証結果を表示します。  
  
## 構文  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|既定のコンストラクターです。|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCMaskedEdit::DisableMask](../Topic/CMFCMaskedEdit::DisableMask.md)|ユーザー入力の検証を無効にします。|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableGetMaskedCharsOnly.md)|`GetWindowText` メソッドでマスク文字のみ取得するかどうかを指定します。|  
|[CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md)|マスク エディット コントロールを初期化します。|  
|[CMFCMaskedEdit::EnableSelectByGroup](../Topic/CMFCMaskedEdit::EnableSelectByGroup.md)|マスク エディット コントロールにより、ユーザー入力の特定のグループを選択するか、またはすべてのユーザー入力を選択するかを指定します。|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableSetMaskedCharsOnly.md)|テキスト検証時の比較対象をマスク文字に限定するか、マスク全体にするかを指定します。|  
|`CMFCMaskedEdit::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md)|マスク エディット コントロールから検証済みのテキストを取得します。|  
|[CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md)|ユーザーが入力できる有効な文字の文字列を指定します。|  
|[CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md)|マスク エディット コントロールにプロンプトを表示します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCMaskedEdit::IsMaskedChar](../Topic/CMFCMaskedEdit::IsMaskedChar.md)|指定された文字を、対応するマスク文字と比較して検証するために、フレームワークによって呼び出されます。|  
  
## 解説  
 アプリケーションで `CMFCMaskedEdit` コントロールを使用するには、次の手順を実行します。  
  
 1.  ウィンドウ クラスに `CMFCMaskedEdit` オブジェクトを埋め込みます。  
  
 2.  [CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md) メソッドを呼び出して、マスクを指定します。  
  
 3.  [CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md) メソッドを呼び出して、有効な文字のリストを指定します。  
  
 4.  [CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md) メソッドを呼び出して、マスク エディット コントロールの既定のテキストを指定します。  
  
 5.  [CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md) メソッドを呼び出して、検証済みのテキストを取得します。  
  
 1 つ以上のメソッドを呼び出してマスク、有効な文字、および既定のテキストを初期化しない場合、マスク エディット コントロールは標準のエディット コントロールのように動作します。  
  
## 使用例  
 `EnableMask` メソッドを使用してマスク エディット コントロールのマスクを作成し、`SetValidChars` メソッドを使用してユーザーが入力できる有効な文字の文字列を指定し、さらに `SetWindowText` メソッドを使用してマスク エディット コントロールにプロンプトを表示することで、マスク \(電話番号など\) を設定する方法を次の例に示します。  この例では [新しいコントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_NewControls#11](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#11)]  
[!CODE [NVC_MFC_NewControls#12](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#12)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CEdit](../Topic/CEdit%20Class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## 必要条件  
 **ヘッダー :** afxmaskededit.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CEdit クラス](../Topic/CEdit%20Class.md)