---
title: "関数のインターフェイス | Microsoft Docs"
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
  - "ICommandTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "関数のインターフェイス"
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 関数のインターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンド ソース オブジェクトからコマンドを受信するインターフェイスには、ユーザー コントロールを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
interface class ICommandTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ICommandTarget::Initialize](#icommandtarget__initialize)|コマンド ターゲット オブジェクトを初期化します。|  
  
## <a name="remarks"></a>コメント  
 MFC の表示では、ユーザー コントロールをホストするときに [CWinFormsView](../../mfc/reference/cwinformsview-class.md) ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンド (フレームのメニュー項目やツール バー ボタンなど) を処理できるようにします。 実装することによって `ICommandTarget`, 、ユーザー コントロールへの参照を提供する、 [ICommandSource](../../mfc/reference/icommandsource-interface.md) オブジェクトです。  
  
 参照してください [方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) を使用する方法の例については `ICommandTarget`です。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  
  
##  <a name="a-nameicommandtargetinitializea-icommandtargetinitialize"></a><a name="icommandtarget__initialize"></a> ICommandTarget::Initialize  
 コマンド ターゲット オブジェクトを初期化します。  
  
```  
void Initialize(ICommandSource^ cmdSource);

 
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdSource`  
 コマンド ソース オブジェクトへのハンドル。  
  
### <a name="remarks"></a>コメント  
 MFC ビューのユーザー コントロールをホストしている場合、CWinFormsView を MFC のコマンドを処理できるようにするユーザー コントロールにコマンドおよび更新コマンド UI メッセージをルーティングします。  
  
 このメソッドは、コマンドのターゲット オブジェクトを初期化し、指定されたコマンド ソース オブジェクト cmdSource に関連付けます。 ユーザー コントロール クラスの実装で呼び出す必要があります。 初期化時に、呼び出し元の ICommandSource::AddCommandHandler Initialize 実装では、コマンド ソース オブジェクトとコマンド ハンドラーを登録してください。 参照してください方法: これを行う初期化を使用する方法の例については、Windows フォーム コントロールにコマンド ルーティングを追加します。  
  
## <a name="see-also"></a>「  
 [方法: コマンドの追加にルーティングする Windows フォーム コントロール](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandSource インターフェイス](../../mfc/reference/icommandsource-interface.md)



