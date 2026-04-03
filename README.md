# TimeLock-10
TimeLock.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract TimeLock {
    uint public unlockTime;

    constructor(uint _time) {
        unlockTime = block.timestamp + _time;
    }

    function canWithdraw() public view returns (bool) {
        return block.timestamp >= unlockTime;
    }
}
