import { Button } from "@/components/ui/button"; import { Card, CardContent } from "@/components/ui/card"; import { FaWallet } from "react-icons/fa";

export default function UICCoinLandingPage() { return ( <div className="min-h-screen bg-gradient-to-br from-blue-900 to-black text-white p-6"> <div className="max-w-4xl mx-auto grid gap-8"> {/* Hero Section */} <div className="text-center space-y-4"> <img src="/uic-logo.png" alt="UIC Coin Logo" className="w-28 mx-auto rounded-full" /> <h1 className="text-4xl font-bold">UIC Coin</h1> <p className="text-lg">A Community-Driven Future of Finance</p> </div>

{/* Tokenomics */}
    <Card className="bg-gray-900 border border-gray-700">
      <CardContent className="p-6 space-y-2">
        <h2 className="text-2xl font-semibold">Tokenomics</h2>
        <ul className="list-disc list-inside text-white/80">
          <li>Total Supply: 1,00,00,000 UIC</li>
          <li>Symbol: UIC</li>
          <li>Decimals: 18</li>
          <li>Community Owned</li>
        </ul>
      </CardContent>
    </Card>

    {/* Contract Info */}
    <Card className="bg-gray-900 border border-gray-700">
      <CardContent className="p-6 space-y-2">
        <h2 className="text-xl font-semibold">Smart Contract</h2>
        <p className="break-words text-white/80">
          0xb55d3128919d4576aaa3d390638490a053cdea13
        </p>
        <a
          href="https://testnet.bscscan.com/token/0xb55d3128919d4576aaa3d390638490a053cdea13"
          target="_blank"
          rel="noopener noreferrer"
          className="text-blue-400 underline"
        >
          View on BscScan Testnet
        </a>
      </CardContent>
    </Card>

    {/* Add to MetaMask */}
    <div className="text-center">
      <Button
        onClick={() => {
          if (window.ethereum) {
            window.ethereum.request({
              method: "wallet_watchAsset",
              params: {
                type: "ERC20",
                options: {
                  address: "0xb55d3128919d4576aaa3d390638490a053cdea13",
                  symbol: "UIC",
                  decimals: 18,
                  image: "https://yourdomain.com/uic-logo.png",
                },
              },
            });
          }
        }}
        className="text-white bg-yellow-500 hover:bg-yellow-600 rounded-full px-6 py-3 flex items-center gap-2"
      >
        <FaWallet className="text-xl" /> Add UIC to MetaMask
      </Button>
    </div>

    {/* Whitepaper Link */}
    <div className="text-center">
      <a
        href="/UIC_Whitepaper.pdf"
        className="text-white underline text-lg"
        target="_blank"
        rel="noopener noreferrer"
      >
        View Whitepaper
      </a>
    </div>
  </div>
</div>

); }

# UICCOIN-website
