import { ConnectButton } from "@rainbow-me/rainbowkit";
import styles from "./Header.module.css";

export function Header(): JSX.Element {
  return (
    <header className={styles.wrapper}>
      <ConnectButton />
    </header>
  );
}
import type { Metadata } from "next";
import { Header } from "@/modules/common/components/Header";
import { WalletProvider } from "@/modules/wagmi/components/WalletProvider";
import "@rainbow-me/rainbowkit/styles.css";
import "./globals.css";

export const metadata: Metadata = {
  title: "WAGMI + RainbowKit Demo App",
  description:
    "A Demo app for minting NFTs on Soneium Minato by using WAGMI and Rainbowkit.",
};

export default function RootLayout({
  children,
}: Readonly<{
  children: React.ReactNode;
}>) {
  return (
    <html lang="en">
      <body>
        <WalletProvider>
          <Header />
          {children}
        </WalletProvider>
      </body>
    </html>
  );
}
