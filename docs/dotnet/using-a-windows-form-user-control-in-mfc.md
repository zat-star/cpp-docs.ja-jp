---
title: "MFC での Windows フォーム ユーザー コントロールの使用 | Microsoft Docs"
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
  - "Windows フォームのサポートの MFC [C++]"
  - "相互運用性 [C++] MFC での Windows フォーム"
  - "相互運用性 [C++] MFC"
  - "相互運用 [C++] MFC での Windows フォーム"
  - "相互運用 [C++] MFC"
  - "Windows フォーム [C++] MFC をサポートします。"
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# MFC での Windows フォーム ユーザー コントロールの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC Windows フォーム サポート クラスを使用してホストできます Windows フォーム コントロール、MFC アプリケーション内で MFC のダイアログ ボックスまたはビュー内で ActiveX コントロールとして。 さらに、Windows フォームのフォームの場合は、MFC ダイアログ ボックスとしてホストされていることができます。  
  
 次のセクションで説明する方法。  
  
-   MFC ダイアログ ボックスでの Windows フォーム コントロールをホストします。  
  
-   MFC ビューとして Windows フォーム ユーザー コントロールをホストします。  
  
-   MFC ダイアログ ボックスとして、Windows フォームをホストします。  
  
> [!NOTE]
>  MFC Windows フォームの統合は、MFC と動的にリンクするプロジェクトでのみ機能 (プロジェクトの AFXDLL が定義されている場合)。  
  
> [!NOTE]
>  MFC Windows フォーム インターフェイス (mfcmifc80.dll) DLL のプライベート (変更) コピーを使用してアプリケーションをビルドするときに、ベンダー キーを使って Microsoft キーを交換しない限り、GAC にインストールするには失敗します。 アセンブリの署名の詳細については、次を参照してください。 [アセンブリを使用したプログラミング](../Topic/Programming%20with%20Assemblies.md) と [厳密な名前のアセンブリ (アセンブリ署名) (C + +/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)します。  
  
 Windows フォームを使用するサンプル アプリケーションでは、次を参照してください。 [「: Windows フォームで .NET Framework リソースを示します](http://msdn.microsoft.com/ja-jp/ac932aed-5502-4667-be29-709bca435317), 、[電卓のサンプル: Windows フォームのポケット計算機](http://msdn.microsoft.com/ja-jp/2283b516-3b7e-45f2-80c4-fdcfb366ce25), 、および [Scribble サンプル: MDI 描画アプリケーション](http://msdn.microsoft.com/ja-jp/f025da3e-659b-4222-b991-554a1b8b2358)します。  
  
 Windows フォームと MFC の組み合わせを示すサンプル アプリケーションを参照してください。 [MFC と Windows フォーム統合](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)します。  
  
 MFC アプリケーションでは、Windows フォームを使用する場合は、アプリケーションと共に mfcmifc90.dll を再配布する必要があります。 詳細については、次を参照してください。 [MFC ライブラリの再配布](../ide/redistributing-the-mfc-library.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [MFC ダイアログ ボックスで Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)  
  
 [MFC ビューとして Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)  
  
 [MFC ダイアログ ボックスとして Windows フォーム ユーザー コントロールのホスト](../Topic/Hosting%20a%20Windows%20Form%20User%20Control%20as%20an%20MFC%20Dialog%20Box.md)  
  
## <a name="reference"></a>参照  
 [関数のクラス](../mfc/reference/cwinformscontrol-class.md)  
  
 [CWinFormsDialog クラス](../Topic/CWinFormsDialog%20Class.md)  
  
 [CWinFormsView クラス](../mfc/reference/cwinformsview-class.md)  
  
 [ICommandSource インターフェイス](../mfc/reference/icommandsource-interface.md)  
  
 [関数のインターフェイス](../mfc/reference/icommandtarget-interface.md)  
  
 [ICommandUI インターフェイス](../mfc/reference/icommandui-interface.md)  
  
 [IView インターフェイス](../Topic/IView%20Interface.md)  
  
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)  
  
 [CommandUIHandler](../Topic/CommandUIHandler%20Delegate.md)  
  
 [DDX_ManagedControl](../Topic/DDX_ManagedControl.md)  
  
 [UICheckState](../Topic/UICheckState%20Enumeration.md)  
  
## <a name="related-sections"></a>関連項目  
 [Windows フォーム](../Topic/Windows%20Forms.md)  
  
 [Windows フォーム コントロール](../Topic/Windows%20Forms%20Controls.md)  
  
 [ASP.NET ユーザー コントロール](../Topic/ASP.NET%20User%20Controls.md)  
  
## <a name="see-also"></a>「  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)   
 [フォーム ビュー](../Topic/Form%20Views%20\(MFC\).md)