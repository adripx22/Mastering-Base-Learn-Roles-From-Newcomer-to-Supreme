# Mastering-Base-Learn-Roles-From-Newcomer-to-Supreme
The Base ecosystem is growing faster than ever, and the Base Guild roles on Discord have become a fun and rewarding way to get involved. By completing smart contract challenges on the Base Sepolia testnet, you can unlock roles that not only reflect your progress but may also bring benefits in the community.  In this blog post
cod:
// SPDX-License-Identifier: UNLICENSED
pragma solidity ^0.8.23;

interface IBasicContractTest {
    function adder(
        uint _a,
        uint _b
    ) external returns (uint result, bool success);

    function subtractor(
        uint _a,
        uint _b
    ) external returns (uint result, bool success);
}

contract SafeMathContract is IBasicContractTest {
    function adder(
        uint _a,
        uint _b
    ) external pure override returns (uint result, bool success) {
        if (type(uint).max - _a < _b) {
            return (0, true);
        } else {
            result = _a + _b;
            return (result, false);
        }
    }

    function subtractor(
        uint _a,
        uint _b
    ) external pure override returns (uint result, bool success) {
        if (_b > _a) {
            return (0, true);
        } else {
            result = _a - _b;
            return (result, false);
        }
    }
}
