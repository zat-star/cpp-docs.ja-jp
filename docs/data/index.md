---
layout: LandingPage
title: "Visual C++ でのデータ アクセス"
translationtype: Human Translation
ms.sourcegitcommit: f9e63f47a8df69b52a6a12688e84602981d20dae
ms.openlocfilehash: 807cf772d632f66f74a210985ff611fc31ee594a
ms.lasthandoff: 03/21/2017

---
# <a name="data-access-in-visual-c"></a>Visual C++ でのデータ アクセス

ほぼすべてのデータベース製品 (SQL および NoSQL) には、ネイティブ C++ アプリケーション用のインターフェイスが用意されています。 業界標準のインターフェイスは ODBC です。ODBC は主要な SQL データベース製品と多数の NoSQL 製品でサポートされています。 Microsoft 以外の製品の詳細については、ベンダーにお問い合わせください。 さまざまなライセンス条項のサードパーティのライブラリも使用できます。

Microsoft は、2011 年以降、オンプレミスとクラウドの両方で Microsoft SQL Server データベースに接続するネイティブ アプリケーションの標準として ODBC を調整してきました。 詳細については、「[データ アクセス プログラミング \(MFC-ATL\)](data-access-programming-mfc-atl.md)」を参照してください。 C++/CLI ライブラリでは、ネイティブ ODBC ドライバーまたは ADO.NET を使用できます。 詳細については、「[ADO.NET によるデータ アクセス (C++/CLI)](/dotnet/data-access-using-adonet-cpp-cli.md)」と「[Visual Studio でのデータ アクセス](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio)」を参照してください。

<ul class="panelContent cardsF">
<li>
        <a href="/azure/sql-database/sql-database-develop-cplusplus-simple">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/azure/media/index/SQLDatabase.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>C および C++ を使用して SQL Database に接続する</h3>
                        <p>C または C++ アプリケーションから Azure SQL Database に接続する</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://github.com/Azure/azure-storage-cpp">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/azure/media/index/Storage.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>C++ 用 Microsoft Azure Storage クライアント ライブラリ</h3>
                        <p>[Azure Storage](/azure/storage/storage-introduction) は、顧客のニーズに合う耐久性、可用性、スケーラビリティを必要とする最新のアプリケーション向けのクラウド ストレージ ソリューションです。 C++ 用 Azure Storage クライアント ライブラリを使用して C++ から Azure Storage に接続します。</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_drivers.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>ODBC Driver 13.1 for SQL Server – Windows のリリース</h3>
                        <p>最新の ODBC ドライバーには、C/C++ ベースのアプリケーション向けの Microsoft SQL Server 2016 Microsoft Azure SQL Database に対する堅牢なデータ アクセス機能があります。 常時暗号化、Azure Active Directory、AlwaysOn 可用性グループなどの機能をサポートしています。 また、Mac OS と Linux でも使用できます。</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://msdn.microsoft.com/library/ms130892.aspx">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_api.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>SQL Server Native Client</h3>
                        <p>SQL Server Native Client は、単体のデータ アクセス アプリケーション プログラミング インターフェイス (API) です。OLE DB と ODBC の両方で使用され、SQL Server 2005 から SQL Server 2014 をサポートしています。 新しいアプリケーションでは、ODBC Driver 13.1 for SQL Server を使用することをお勧めします。</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="data-access-programming-mfc-atl.md">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_api.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>データ アクセス プログラミング</h3>
                        <p>Visual C++ を使用したレガシ データ アクセス プログラミングについて説明します。このプログラミングには、データベース API での処理が簡単になるように、ATL (Active Template Class Library)、MFC (Microsoft Foundation Class) ライブラリなどのクラス ライブラリの&1; つを使用することをお勧めします。</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="odbc/open-database-connectivity-odbc.md">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_multi-connect.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>ODBC (Open Database Connectivity)</h3>
                        <p>MFC (Microsoft Foundation Class) ライブラリには、ODBC (Open Database Connectivity) を使用したプログラミング用のクラスが用意されています。</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="oledb/ole-db-programming.md">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_generic-database.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>OLE DB プログラミング</h3>
                        <p>OLE DB データベース テクノロジおよび OLE DB テンプレート ライブラリに関する概念説明のトピックへのリンクを提供します。 (リンクされているサーバーがあるシナリオを除き、新しいアプリケーションに OLE DB は推奨されません)。</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    
</ul>

---

<h2>参照</h2>

<ul class="panelContent cardsW">
 <li>
        <a href="https://azure.microsoft.com/develop/cpp/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Microsoft Azure C および C++ デベロッパー センター</h3>
                        <p>Azure を使用すると、柔軟性、スケーラビリティ、信頼性の高い C++ アプリケーションを好みのツールで容易に構築できます。</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>C++ から Blob Storage を使用する方法</h3>
                        <p>Azure BLOB Storage は、非構造化データをオブジェクト/BLOB としてクラウドに格納するサービスです。 Blob Storage は、ドキュメント、メディア ファイル、アプリケーション インストーラーなど、任意の種類のテキストまたはバイナリ データを格納できます。 Blob Storage は、オブジェクト ストレージとも呼ばれます。</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>ODBC プログラマーズ リファレンス</h3>
                        <p>ODBC インターフェイスは、C プログラミング言語で使用するために設計されています。 ODBC インターフェイスは、SQL ステートメント、ODBC 関数呼び出し、C プログラミングという&3; つの領域で使用されます。</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3><a href="https://www.microsoft.com/download/details.aspx?id=53339" title="Microsoft® ODBC Driver 13.1 for SQL Server® - Windows Download Page">ODBC Driver 13.1 for SQL Server</a></h3>
                        <p>Microsoft ODBC Driver 13.1 for SQL Server は、アプリケーションがネイティブ コード API を使用して Microsoft SQL Server 2008、SQL Server 2008 R2、SQL Server 2012、SQL Server 2016、Analytics Platform System、Azure SQL Database および Azure SQL Data Warehouse に接続するためのランタイム サポートを含む、単一のダイナミック リンク ライブラリ (DLL) です。 ここからドライバーをダウンロードしてください。</p>
                    </div>
                </div>
            </div>
        </div>        
    </li>
    
</ul>
