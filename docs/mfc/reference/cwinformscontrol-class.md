---
title: "CWinFormsControl クラス | Microsoft Docs"
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
  - "CWinFormsControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsControl クラス"
  - "MFC [C++], Windows フォームのサポート"
  - "Windows フォーム [C++], MFC サポート"
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinFormsControl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows フォーム コントロールのホスティング用の基本機能を提供します。  
  
## 構文  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### パラメーター  
 `TManagedControl`  
 MFC アプリケーションに表示する .NET Framework Windows フォーム コントロール。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CWinFormsControl::CWinFormsControl](../Topic/CWinFormsControl::CWinFormsControl.md)|MFC Windows フォーム コントロールのラッパー オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md)|MFC コンテナーに Windows フォーム コントロールを作成します。|  
|[CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md)|Windows フォーム コントロールへのポインターを取得します。|  
|[CWinFormsControl::GetControlHandle](../Topic/CWinFormsControl::GetControlHandle.md)|Windows フォームのコントロールのハンドルを取得します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CWinFormsControl::operator \-\>](../Topic/CWinFormsControl::operator%20-%3E.md)|式に置き換えます [CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md)。|  
|[CWinFormsControl::operator TManagedControl^](../Topic/CWinFormsControl::operator%20TManagedControl%5E.md)|Windows フォームのコントロールに型をとしてキャスト ポインター。|  
  
## 解説  
 `CWinFormsControl` のクラスは、Windows フォーム コントロールのホスティング用の基本機能を提供します。  
  
 Windows フォームの使い方の詳細については、「[MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。  
  
 使用する MFC コードは、ウィンドウ ハンドルが必要である \(通常 `m_hWnd`に格納されている、キャッシュできます。  いる Windows フォーム コントロールのプロパティは、基になる Win32 `Window` が `DestroyWindow` と `CreateWindow`を使用して破棄され、再作成する必要があります。  MFC は Windows `m_hWnd` のメンバーを更新する実装のハンドルをコントロールの `Destroy` と `Create` フォームのイベント。  
  
> [!NOTE]
>  MFC Windows は、AFXDLL が定義されているか\) MFC と動的にリンクするプロジェクトにのみ統合する作業を付けた。  
  
## 必要条件  
 **ヘッダー:** afxwinforms.h  
  
## 参照  
 [CWinFormsDialog クラス](../Topic/CWinFormsDialog%20Class.md)   
 [CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)