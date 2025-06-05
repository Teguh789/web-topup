import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Input } from "@/components/ui/input";
import { Button } from "@/components/ui/button";
import { Select, SelectTrigger, SelectValue, SelectContent, SelectItem } from "@/components/ui/select";

export default function TopUpPage() {
  const [game, setGame] = useState("");
  const [userId, setUserId] = useState("");
  const [amount, setAmount] = useState("");
  const [payment, setPayment] = useState("");
  const [proof, setProof] = useState(null);

  const handleSubmit = (e) => {
    e.preventDefault();
    alert("Pesanan dikirim! (Simulasi)");
  };

  return (
    <div className="min-h-screen bg-gray-100 p-4 flex justify-center items-center">
      <Card className="w-full max-w-md shadow-xl">
        <CardContent className="space-y-4 py-6">
          <h1 className="text-2xl font-bold text-center">Top Up Game</h1>
          <form onSubmit={handleSubmit} className="space-y-4">
            <div>
              <label className="block mb-1 font-medium">Pilih Game</label>
              <Select onValueChange={setGame}>
                <SelectTrigger>
                  <SelectValue placeholder="Pilih game" />
                </SelectTrigger>
                <SelectContent>
                  <SelectItem value="ml">Mobile Legends</SelectItem>
                  <SelectItem value="ff">Free Fire</SelectItem>
                  <SelectItem value="genshin">Genshin Impact</SelectItem>
                  <SelectItem value="pubg">PUBG Mobile</SelectItem>
                  <SelectItem value="valorant">Valorant</SelectItem>
                </SelectContent>
              </Select>
            </div>
            <div>
              <label className="block mb-1 font-medium">User ID</label>
              <Input value={userId} onChange={(e) => setUserId(e.target.value)} placeholder="Masukkan ID game kamu" required />
            </div>
            <div>
              <label className="block mb-1 font-medium">Nominal</label>
              <Select onValueChange={setAmount}>
                <SelectTrigger>
                  <SelectValue placeholder="Pilih nominal top up" />
                </SelectTrigger>
                <SelectContent>
                  <SelectItem value="5">5 Diamonds</SelectItem>
                  <SelectItem value="12">12 Diamonds</SelectItem>
                  <SelectItem value="50">50 Diamonds</SelectItem>
                  <SelectItem value="100">100 Diamonds</SelectItem>
                </SelectContent>
              </Select>
            </div>
            <div>
              <label className="block mb-1 font-medium">Metode Pembayaran</label>
              <Select onValueChange={setPayment}>
                <SelectTrigger>
                  <SelectValue placeholder="Pilih metode pembayaran" />
                </SelectTrigger>
                <SelectContent>
                  <SelectItem value="dana">DANA</SelectItem>
                  <SelectItem value="gopay">GoPay</SelectItem>
                  <SelectItem value="ovo">OVO</SelectItem>
                  <SelectItem value="qris">QRIS</SelectItem>
                  <SelectItem value="transfer">Transfer Bank</SelectItem>
                </SelectContent>
              </Select>
            </div>
            <div>
              <label className="block mb-1 font-medium">Upload Bukti Pembayaran</label>
              <Input type="file" onChange={(e) => setProof(e.target.files[0])} required />
            </div>
            <Button className="w-full" type="submit">Kirim Pesanan</Button>
          </form>
        </CardContent>
      </Card>
    </div>
  );
}
