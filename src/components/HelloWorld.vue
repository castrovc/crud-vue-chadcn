<script setup lang="ts">
import {
  Table,
  TableBody,
  TableCaption,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from "../components/ui/table";
import Button from "./ui/button/Button.vue";
import { toast } from "vue-sonner";

const invoices = [
  {
    invoice: "INV001",
    paymentStatus: "Paid",
    totalAmount: "$250.00",
    paymentMethod: "Credit Card",
  },
  {
    invoice: "INV002",
    paymentStatus: "Pending",
    totalAmount: "$150.00",
    paymentMethod: "PayPal",
  },
  {
    invoice: "INV003",
    paymentStatus: "Unpaid",
    totalAmount: "$350.00",
    paymentMethod: "Bank Transfer",
  },
  {
    invoice: "INV004",
    paymentStatus: "Paid",
    totalAmount: "$450.00",
    paymentMethod: "Credit Card",
  },
  {
    invoice: "INV005",
    paymentStatus: "Paid",
    totalAmount: "$550.00",
    paymentMethod: "PayPal",
  },
  {
    invoice: "INV006",
    paymentStatus: "Pending",
    totalAmount: "$200.00",
    paymentMethod: "Bank Transfer",
  },
  {
    invoice: "INV007",
    paymentStatus: "Unpaid",
    totalAmount: "$300.00",
    paymentMethod: "Credit Card",
  },
];
</script>

<template>
  <div class="p-10 w-full grid items-center justify-center">
    <Table class="bg-slate-800 w-full border border-white shadow-lg rounded-md">
      <TableCaption>A list of your recent invoices.</TableCaption>
      <TableHeader class="bg-gray-900">
        <TableRow class="text-white">
          <TableHead class="w-[100px] text-white text-xl"> Invoice </TableHead>
          <TableHead class="text-white text-xl">Status</TableHead>
          <TableHead class="text-white text-xl">Method</TableHead>
          <TableHead class="text-white text-xl text-right"> Amount </TableHead>
        </TableRow>
      </TableHeader>
      <TableBody>
        <TableRow
          v-for="invoice in invoices"
          class="text-white"
          :key="invoice.invoice"
        >
          <TableCell class="font-medium text-white">
            {{ invoice.invoice }}
          </TableCell>
          <TableCell>{{ invoice.paymentStatus }}</TableCell>
          <TableCell>{{ invoice.paymentMethod }}</TableCell>
          <TableCell class="text-right">
            {{ invoice.totalAmount }}
          </TableCell>
        </TableRow>
      </TableBody>
    </Table>
    <Button
      class="mt-10"
      variant="secondary"
      @click="
        () => {
          toast('This is a toast', {
            description: 'Example how to use the toast component',
            action: {
              label: 'Undo',
              onClick: () => console.log('Undo'),
            },
          });
        }
      "
      >Sonner example</Button
    >
  </div>
</template>
