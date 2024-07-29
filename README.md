# @barkprotocol/blinks-react-native

**@barkprotocol/blinks-react-native** is a tailored React Native library for integrating Solana actions with the BARK Protocol. This package extends [Dialect Labs' Blinks React Native](https://github.com/dialectlabs/blinks-react-native) with specialized support for BARK, Solana actions and blockchain interactions.

## Table of Contents

- [Installation](#installation)
- [Configuration](#configuration)
  - [Importing and Wrapping](#importing-and-wrapping)
  - [Using Solana Actions](#using-solana-actions)
- [Security and Registry](#security-and-registry)
  - [Why a New Registry is Needed](#why-a-new-registry-is-needed)
  - [Registration Status](#registration-status)
  - [Rendering Blinks](#rendering-blinks)
  - [Register Your Action](#register-your-action)
  - [Registry Schedule](#registry-schedule)
  - [Work with Us](#work-with-us)
- [BARK Use Cases](#bark-use-cases)
  - [Donation](#donation)
  - [Charity Aid Campaign](#charity-aid-campaign)
  - [Fundraising](#fundraising)
  - [Web3 Payments](#web3-payments)
  - [Purchasing BARK Tokens](#purchasing-bark-tokens)
  - [Tiered Memberships](#tiered-memberships)
  - [CNFTs and Tokens](#cnfts-and-tokens)
- [Example](#example)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)
- [Acknowledgments](#acknowledgments)

## Installation

To integrate `@barkprotocol/blinks-react-native` into your React Native project, run one of the following commands:

### Using npm

```bash
npm install @barkprotocol/blinks-react-native
```

### Using yarn

```bash
yarn add @barkprotocol/blinks-react-native
```

## Configuration

### Importing and Wrapping

Wrap your app or components with the `BlinksProvider` to enable context for Blinks.

```javascript
import React from 'react';
import { BlinksProvider } from '@barkprotocol/blinks-react-native';
import App from './App';

const Root = () => (
  <BlinksProvider>
    <App />
  </BlinksProvider>
);

export default Root;
```

### Using Solana Actions

Use the `useBlinks` hook to handle Solana actions in your components.

```javascript
import React from 'react';
import { Button, Text, View } from 'react-native';
import { useBlinks } from '@barkprotocol/blinks-react-native';

const MyComponent = () => {
  const { performAction } = useBlinks();

  const handleAction = async () => {
    try {
      await performAction({/* action parameters */});
      alert('Action performed successfully!');
    } catch (error) {
      console.error('Error performing action:', error);
    }
  };

  return (
    <View>
      <Text>Perform Solana Action</Text>
      <Button title="Perform Action" onPress={handleAction} />
    </View>
  );
};

export default MyComponent;
```

## Security and Registry

### Why a New Registry is Needed

Traditional wallet extensions rely on URL origins to determine trustworthiness. Actions, however, can originate from various providers, making a new verification system essential.

### Registration Status

The Dialect registry at [https://dial.to/registry](https://dial.to/registry) categorizes Actions as follows:

- **trusted**: Verified and approved by the registration committee.
- **blocked**: Flagged as malicious by the community.
- **none**: Not yet registered.

### Rendering Blinks

Wallets using Blinks clients reference the registry to display Blinks based on their status:

- **Neutral**: For trusted actions.
- **Yellow Warning**: For unregistered actions (status `none`).
- **Red**: For blocked actions (known to be malicious).

Phantom, Backpack, and other wallets may choose not to display Blinks with status `none` or `blocked` to prioritize user safety.

## BARK Use Cases

### Donation

Enable seamless donations through your app. Integrate Solana-based actions to facilitate secure and transparent contributions to various causes.

### Charity Aid Campaign

Manage and execute charity campaigns using BARK Protocol. Engage users in interactive campaigns where they can contribute to charitable causes efficiently.

### Fundraising

Support fundraising activities with BARK actions. Manage token sales, auctions, or other blockchain-based fundraising methods to raise funds effectively.

### Web3 Payments

Integrate web3 payment solutions for services or products. Facilitate fast, secure payments through Solana transactions, enhancing user experience.

### Purchasing BARK Tokens

Allow users to purchase BARK tokens directly through your app. Integrate token purchase mechanisms to enable secure transactions for acquiring BARK tokens.

### Tiered Memberships

Implement tiered membership systems using BARK Protocol. Manage memberships with varying benefits, ensuring transparent and secure transactions.

### CNFTs and Tokens

Facilitate the purchase, trade, and management of CNFTs (Crypto Non-Fungible Tokens) and other tokens. Leverage Solana actions for efficient and secure transactions.

## Example

Explore the `example` folder in this repository for a sample React Native project demonstrating how to integrate and utilize the library.

## Contributing

We welcome contributions! Please refer to our [contributing guidelines](CONTRIBUTING.md) for details on how to contribute.

## License

The MIT License. See the [LICENSE](LICENSE) file for details.

## Support

For issues or questions, please open an issue on the [GitHub repository](https://github.com/bark-community/blinks-react-native/issues).

## Acknowledgments

- [Dialect Labs' Blinks React Native](https://github.com/dialectlabs/blinks-react-native) for the original library.
- [Solana](https://solana.com/) for the blockchain platform.

### Work with Us

BARK Protocol aims to create a decentralized, community-driven trust system. Interested in collaborating? Join us on our [community](https://t.me/bark_protocol).

Feel free to adjust or expand based on the specific features and requirements of BARK projects.