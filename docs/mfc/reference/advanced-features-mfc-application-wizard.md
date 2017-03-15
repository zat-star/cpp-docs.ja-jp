---
title: "MFC アプリケーション ウィザードの機能の詳細 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.advanced
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ab9e67efc6fad90f2f9eb140411d063320f09feb
ms.lasthandoff: 02/24/2017

---
# <a name="advanced-features-mfc-application-wizard"></a>[高度な機能] (MFC アプリケーション ウィザード)
このトピックでは、ヘルプや印刷サポートなど、アプリケーションの追加機能のためのオプションを示します。 各セクションで、これらの高度な機能の追加サポートを指定します。  
  
 **状況依存のヘルプ (HTML)**  
 またはをクリックして f1 キーと、ヘルプ メニューを使用して利用できる状況依存のヘルプのヘルプ ファイルのセットを生成、**ヘルプ** ダイアログ ボックスのボタンです。 ヘルプ サポートにはヘルプ コンパイラが必要です。 ヘルプ コンパイラがない場合は、セットアップを再実行することによってインストールできます。  
  
 参照してください[HTML ヘルプ: プログラムの状況依存のヘルプ](../../mfc/html-help-context-sensitive-help-for-your-programs.md)と[ヘルプ ファイル (HTML ヘルプ)](../../ide/help-files-html-help.md)の詳細。  
  
 **印刷と印刷プレビュー**  
 印刷の処理、メンバー関数を呼び出すことによって、印刷と印刷プレビューのコマンドのコードを生成、 [CView クラス](../../mfc/reference/cview-class.md)MFC ライブラリからです。 これらの関数に対するコマンドも、ウィザードによってアプリケーションのメニューに追加されます。 印刷サポートは指定しているアプリケーションでのみ使用できます**ドキュメント/ビュー アーキテクチャ サポート**で、[アプリケーションの種類、MFC アプリケーション ウィザード](../../mfc/reference/application-type-mfc-application-wizard.md)ウィザードのページです。 既定では、ドキュメント/ビュー アプリケーションには印刷サポートが含まれます。  
  
 **オートメーション**  
 アプリケーションが別のアプリケーションに実装されているオブジェクトを操作したり、アプリケーションをオートメーション クライアントに公開したりできるように指定します。  
  
 **ActiveX コントロール**  
 ActiveX コントロールをサポートします (既定値)。 このオプションを選択されず、後で、プロジェクトに ActiveX コントロールを挿入する場合は場合、への呼び出しを追加する必要があります[AfxEnableControlContainer](http://msdn.microsoft.com/library/7aa0b9d2-5329-4bc3-9d41-856e30fe2c2b)をアプリケーションの[場合は](../../mfc/reference/cwinapp-class.md#initinstance)メンバー関数。  
  
 **MAPI (メッセージ API)**  
 アプリケーションでメール メッセージの作成、操作、転送、および格納ができるように指定します。  
  
 **Windows ソケット**  
 TCP/IP ネットワークで通信するアプリケーションを作成するために使用できる Windows ソケットをサポートします。  
  
 **Active Accessibility**  
 サポートが追加されて[IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466)に[CWnd](../../mfc/reference/cwnd-class.md)の派生クラスで、ユーザー補助クライアントと相互運用性ものユーザー インターフェイスのカスタマイズを行うこともできます。  
  
 **コモン コントロール マニフェスト**  
 既定で有効になります。 Microsoft Windows XP 以降のオペレーティング システムに同梱されているコモン コントロール DLL を使用するためのアプリケーション マニフェストを生成します。  
  
 既存のアプリケーションで使用されている以前のバージョンのコモン コントロールが、Version 6 のコモン コントロール DLL によって自動的に更新されることはありません。 Version 6 のコモン コントロール DLL を使用するには、アプリケーションが DLL を読み込むことができるようにするためのアプリケーション マニフェストを作成する必要があります。 Version&6; のコモン コントロール DLL は、Windows XP のテーマもサポートしています。  
  
 また、アプリケーション マニフェストによって、アプリケーションに必要なその他の DLL やその他のバージョンも指定できます。 アプリケーション マニフェストの詳細については、次を参照してください。[分離アプリケーションとサイド バイ サイド アセンブリ](http://msdn.microsoft.com/library/dd408052)で、[!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
 **再起動マネージャーのサポート**  
 サポートが追加されて、 [Windows 再起動マネージャー](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx)します。 このビデオは、MFC から再起動マネージャーを使用する方法を示します:[方法: 新しい再起動マネージャーを使用](http://msdn.microsoft.com/vstudio/ee886407)します。  
  
 **高度なフレーム ペイン**  
 |オプション|説明|  
|------------|-----------------|  
|**エクスプ ローラーのドッキング ペイン**|Visual Studio のようなドッキング ペインを作成**ソリューション エクスプ ローラー**メイン フレーム ウィンドウの左側にします。|  
|**出力 [ドッキング]**|Visual Studio のようなドッキング ペインを作成**出力**メイン フレーム ウィンドウの下にあるウィンドウです。|  
|**ウィンドウをドッキング可能なプロパティ**|Visual Studio のようなドッキング ペインを作成**プロパティ**メイン フレーム ウィンドウの右側のウィンドウです。|  
|**ナビゲーション ウィンドウ**|メイン フレーム ウィンドウの左側に、Outlook のナビゲーション バーのようなドッキング ペインを作成します。|  
|**キャプション バー**|メイン フレーム ウィンドウの上に、Office 形式のキャプション バーを作成します。|  
  
 **最近使ったファイルの一覧にファイルの数**  
 最近使ったファイルの一覧に表示するファイル数を指定します。 既定値は 4 です。  
  
## <a name="see-also"></a>関連項目  
 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)


