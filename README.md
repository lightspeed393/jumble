# Jumble

Jumble is a script that will jumble your coins to achieve privacy.

Coins are sent from a transparent address to a private address. From that private address to another private address. Finally from that private address back to a transparent address.

(t -> p) (p -> p) (p -> t)

Jumble only makes transactions with 9 or 93 coins. This is done to limit the amount of chain analysis tracking that can be done by comparing similar balances entering private addresses and exiting back to transparent addresses. With every jumble using the same amounts, it greatly adds to the amount of privacy gained by jumbling.

Example:  Jumbling 39.939 coins would be pretty easy to track the original transparent address to the final transparent address because of the specific 39.939 coin amount.

Jumble design is based on [Jumblr](https://developers.komodoplatform.com/basic-docs/smart-chains/smart-chain-api/jumblr.html) by Komodo Platform. It has since been deactivated for Komodo and was never available for assetchains.

## Privacy

Jumble gives you the best privacy when used with Spacecoin (coming soon) because instances will be running often on the network. This increases the number of jumble transactions, which in turn increases privacy. Jumble can be used with any komodo assetchain but keep in mind you could be the only user jumbling on that network, lowering your privacy dramatically.

For maximum privacy, the final address where you receive the jumbled coins should be not be on the same node where the coins were sent from.

## Installing Jumble

```
git clone https://github.com/lightspeed393/jumble
cd ~/jumble
cp jumble.conf.example jumble.conf
nano jumble.conf
```
Fill in the necessary information.

## Using Jumble

To start using Jumble, simply do:

`./jumble`

and it will walk you through the rest.

Jumble will ask you for the address where you'd like to receive your coins. After confirming its correct it will give you a deposit address to send your coins to and take care of the rest.

If you'd rather skip the walk through and specify the deposit and receive addresses yourself, do:

`./jumble_coins depositAddress receiveAddress`

to jumble available balance and stop.

or

`./jumble_coins_loop depositAddress receiveAddress`

to jumble with a loop, where it will keep checking deposit address for balance (similar to normal jumble script).

## Disclaimer

Jumble cannot guarantee 100% privacy for your coins. The more users, the more privacy to be had.

Jumble cannot guarantee the jumbling process will complete successfully. In the event your coins don't make it to the final transparent address, don't panic they are not lost. The first 2 transactions take place on the node jumble is connected to and the coins will remain in that wallet. They can then be recovered from the first transparent address or either of the two private addresses. (I have only have seen this happen a handful of times when the mempool simply lost the transaction when the network blocks were unstable. Will eventually add a check for this to prevent errors.)

## License

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

For details please refer to the [license](https://github.com/lightspeed393/jumble/blob/master/LICENSE).
